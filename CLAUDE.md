# CLAUDE.md — advanced-projects Operating Rules
Last updated: 2026-04-20

These rules apply to every Claude Code session in this repo without exception.

---

## Identity and Profile
- Always use `--profile portfolio-user` for every AWS CLI command
- Verify the profile exists at the start of every session before doing anything else:
  ```
  aws configure list --profile portfolio-user
  ```
- If the profile is missing, stop and tell Jimmy immediately — do not proceed
- Never use the default AWS profile under any circumstances

## GitHub Auth (Recurring Issue)
- gh CLI requires a classic PAT (`ghp_`) with `repo` and `read:org` scopes
- If any gh command fails with an auth error, tell Jimmy to run:
  ```
  echo "TOKEN" | gh auth login --hostname github.com --git-protocol https --with-token
  ```

## Execution Rules
- Explain what you will do before every major action and wait for explicit "go" confirmation
- One file at a time — stop after each file and confirm before moving to the next
- If a file is under 700 lines, print it in full before writing to disk
- If a file is 700+ lines, write directly to disk
- Do not reprint large files after small fixes. One print at the build step is enough.
- Flag problems before they become problems
- Never run destructive git operations (force push, hard reset, rebase on pushed commits, branch delete) without explicit confirmation from Jimmy.
- Never start feature work without reading the current state of `index.html` first
- No scope drift — do only what the current prompt asks, nothing else

## What This Repo Is
- Plain static site — single `index.html`, no frameworks, no build step
- No CloudFormation, no Lambda, no Bedrock, no ingest or query pipelines
- Hosted on S3: `jimmy-advanced-projects` bucket
- CloudFront domain: `https://d2uisqfxjzeo6a.cloudfront.net`
- Deployed via: `aws s3 cp index.html s3://jimmy-advanced-projects/index.html --profile portfolio-user`
- GitHub repo: `git@github.com:jhubb88/advanced-projects.git`

## Page Architecture (as of 2026-04-20)
The page is an **AWS node-web** design — not a card grid. Key implementation details:

**Layout**
- Desktop: two-column flex — left 56% is the radial node map, right 44% is a persistent detail pane
- Node map uses `position: relative` container with absolutely-positioned `.node` divs for each project
- SVG overlay (`#lines-svg`, `position: absolute; inset: 0`) draws connection lines from hub center to each node center via JS `getBoundingClientRect()` — lines are redrawn on click and window resize
- AWS hub is centered in the map area via `transform: translate(-50%, -50%)`
- Mobile breakpoint at 768px: radial map hidden, stacked `#mobile-list` shown instead (tap to select, detail pane renders below)

**Status color system**
- Live: `#22c55e` (green) — node border, dot, status badge
- In Build: `#f59e0b` (amber) — node border, dot, status badge
- Planned: `#4b5563` (muted grey) — node border, dot, status badge; node opacity 0.58

**Connection lines**
- Color matches node status; opacity: Live 0.35, In Build 0.28, Planned 0.18
- Selected node line: opacity 0.82, stroke-width 1.5

**Detail pane**
- Populated by JS from the `projects` data array at the top of the `<script>` block
- Default selection on load: RAG Knowledge Chatbot
- Button logic: Live → Live Demo + Architecture; In Build → no buttons; Planned → no CTA row
- Case Study button was dropped for V1 — no fake CTAs for content that doesn't exist

**Architecture modals (RAG + FieldIQ)**
- Modal section labels: `color: var(--dim)` (`#64748b`) — same style as STACK / KEY POINTS in detail pane
- Bullet dashes `—`: `color: var(--dim)`
- Modal panel border: `1px solid var(--border)` (`#30363d`)
- Do NOT use `#6d3fc0`, `#4a2d8c`, or any purple on modal elements

**Dead variables — do not reintroduce**
The following CSS variables from the old purple card-grid design were removed and must not be added back:
- `--card-bg` (`#3b1f6e`)
- `--card-border` (`#6d3fc0`)
- `--card-hover-bg` (`#4e2a8e`)

## Documentation
This repo does not have a phase-based planning doc. Changes are tracked via git commits and CONTEXT.md updates only.

## Deployment Pattern
- Static file upload only: `aws s3 cp index.html s3://jimmy-advanced-projects/index.html --profile portfolio-user`
- Always use `--profile portfolio-user`
- Do NOT run any deployment command without Jimmy confirming first
- Deploys to this site MUST be followed by a CloudFront invalidation:
  ```
  aws cloudfront create-invalidation \
    --distribution-id E1VZ0ELKDC3LN0 \
    --paths "/*" \
    --profile portfolio-user
  ```

## Portfolio Context
- The portfolio-wide infrastructure reference lives at:
  `/mnt/c/Users/jimmy/Desktop/Projects/portfolio-context/CONTEXT.md`
  GitHub: https://github.com/jhubb88/portfolio-context
- At the end of every session, check if any of the following changed:
  - Project status or content
  - Live URLs
  - GitHub repos
  - Known issues or blockers
- If anything changed, update CONTEXT.md and commit with:
  `chore: update portfolio context — [brief description of what changed]`
- Push to origin main

## Session Wrap-Up
- Write a session wrap-up to `sessions/YYYY-MM-DD-wrap.md` at the end of every session
- Create the `sessions/` directory if it does not exist
- Never end a session without a wrap-up file
- Wrap-up must include: what was completed, what was skipped, errors hit, and exact next steps

## Local Path
- This project: `/mnt/c/Users/jimmy/Desktop/Projects/advanced-projects/`
- Portfolio context: `/mnt/c/Users/jimmy/Desktop/Projects/portfolio-context/`
- All projects: `/mnt/c/Users/jimmy/Desktop/Projects/`

## Commit Conventions
- Format: conventional commits — `feat:`, `fix:`, `docs:`, `chore:`
- Never commit `index.html` without reading it first this session
- Never commit credentials, `.env`, or any secrets
- Always push to `origin main` after committing unless Jimmy says otherwise
