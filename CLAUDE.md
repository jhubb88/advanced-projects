# CLAUDE.md — advanced-projects Operating Rules
Last updated: 2026-04-17

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
