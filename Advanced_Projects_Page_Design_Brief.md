# Advanced Projects Page — Final Design & Interaction Brief

## 1) Project identity

This page is **separate** from the Linux Ops Command Copilot product brief.

It is a portfolio experience for showcasing Jimmy Hubbard’s advanced AWS-native projects through an interactive architecture map.

### Purpose
The page should feel like:
- an interactive cloud architecture explorer
- an AWS-native project network
- a systems-focused portfolio experience
- premium, clean, and memorable

It should **not** feel like:
- a generic project-card grid
- a game UI
- a cyberpunk dashboard
- a fake SOC screen
- a flashy concept render

---

## 2) Final concept

### Core idea
Use a central AWS hub with connected project nodes around it.

### Interaction
Clicking a project node updates the project detail surface.

### Why this concept won
It is:
- more memorable than the old purple card grid
- more aligned with systems/cloud engineering
- more visually distinctive
- more “Jimmy” than a standard portfolio grid

---

## 3) Final direction locked

### Keep
- AWS hub in the center
- “Advanced AI Systems on AWS” platform labeling
- connected project nodes
- project status logic
- a dedicated detail area tied to node selection
- a dark premium visual foundation
- a clean enterprise/cloud architecture feel

### Avoid
- too much glow
- fake HUD clutter
- game-like styling
- noisy corner graphics
- overly dramatic cyber effects
- stock-graphic feeling backgrounds

---

## 4) Final page structure

### Top bar
Minimal top navigation.

### Main hero/explorer section
A wide interactive layout made of:
- **left / center:** AWS hub + project network
- **right:** selected project detail area

### Below the explorer (optional, secondary)
Can include:
- project methodology
- architecture principles
- AWS-native design philosophy
- supporting project links or screenshots

The network experience remains the main attraction.

---

## 5) Visual style direction

## Final style
A clean enterprise-style AWS project map.

### Desired feel
- cloud architecture page
- premium project explorer
- modern, restrained, technical
- interactive, but not gimmicky

### Foundation
- dark navy / charcoal background
- subtle grid or soft structural texture only
- restrained line work
- clean node cards
- calm accent use

### Avoid
- cyberpunk look
- tactical shooter UI
- mech cockpit energy
- excessive saturation
- decorative clutter

---

## 6) Central hub

### Center object
AWS cloud mark in the center.

### Supporting label
Use **“Advanced AI Systems on AWS”** beneath or directly associated with the hub.

### Meaning
The center is not just branding.  
It represents the shared platform/environment that the surrounding projects are built on.

### Important rule
The page is still Jimmy’s portfolio.  
AWS is the common backbone, not the star over the projects themselves.

---

## 7) Project nodes

### Initial nodes
- RAG Knowledge Chatbot
- FieldIQ
- Linux Ops Command Copilot
- AI Security Assessment Agent
- Cloud Incident Copilot

### Node rules
- use a small number of nodes
- keep spacing intentional
- avoid clutter
- each node should have a clear label
- each node may include a small icon
- each node should visually reflect project state

### Status system
- **Live** → brighter and more active
- **In Build** → controlled in-progress accent
- **Planned** → quieter, more muted

### Important note
No duplicate node names or repeated projects.

---

## 8) Node interaction behavior

### On hover
- subtle highlight
- slightly brighter node outline or surface
- optional short tooltip/preview

### On click
- selected node becomes active
- project detail pane updates
- only one selected project at a time
- network stays visible while details change

### Selected-state behavior
- selected node gets stronger outline or active state
- connected line may brighten slightly
- detail pane updates without full page transition

---

## 9) Detail-surface decision

After exploration, the selected-project detail UI should behave like a **dedicated project explorer pane**, not a popup modal.

### Final decision
Use a persistent detail surface on the right side of the network area.

### Why
- keeps the network visible
- feels more like an architecture explorer
- less template-like than a floating modal
- more believable as a real site

### Important styling rule
Even though it is a pane, it should not feel like a generic SaaS card.  
It should feel like part of the architecture interface.

---

## 10) Detail pane content structure

### Recommended content order
1. Status
2. Project title
3. Short summary
4. Sectioned project information
5. Stack / platform tags
6. Actions
7. Key points / highlights

### Strong content sections
- **Purpose**
- **Stack**
- **Architecture**
- **Key Points**

This label-driven structure feels more like a selected-project briefing and less like a template card.

---

## 11) Button logic

### Live projects
- **Live Demo**
- **Architecture**

### In Build projects
- no buttons

### Planned projects
- lighter treatment
- no fake full CTA row
- optional single muted concept/notes treatment if needed

### Note
Case Study button dropped for V1 across all projects. No fake CTAs for unfinished work.

### Why
This keeps trust high and avoids pretending unfinished work is fully explorable.

---

## 12) Exact panel copy direction by project

## RAG Knowledge Chatbot
### Status
Live

### Summary
Serverless RAG chatbot built on AWS for comparing AI responses, testing retrieval flows, and showing production-minded architecture around routing, latency, and scalability.

### Tags
- AWS Bedrock
- SambaNova
- Lambda
- API Gateway
- RAG

### Buttons
- Live Demo
- Architecture

### Key points
- Dual-provider response comparison
- Retrieval + prompt routing workflow
- AWS-native serverless design

---

## FieldIQ
### Status
Live

### Summary
Football analytics platform focused on performance breakdowns, trend analysis, and deeper insight delivery through a clean, data-driven experience.

### Tags
- Analytics
- Sports Data
- Visualization
- Dashboard
- AWS

### Buttons
- Live Demo
- Architecture

### Key points
- Performance trend analysis
- Sports-focused data presentation
- Dashboard-style insight delivery

---

## Linux Ops Command Copilot
### Status
In Build

### Summary
Plain-English to Bash assistant for Linux admin workflows, combining command generation with safety-aware guidance, risk labels, and operational review.

### Tags
- Linux
- React
- AWS Lambda
- API Gateway
- Safety-aware

### Buttons
- none (In Build — V1)

### Key points
- Safety-aware command review
- Structured risk classification
- Serverless backend architecture

---

## AI Security Assessment Agent
### Status
Planned

### Summary
Cloud security review concept focused on identifying configuration risk, explaining findings clearly, and surfacing practical remediation priorities.

### Tags
- Security
- Findings
- Risk Review
- AWS
- Remediation

### Key points
- Misconfiguration review
- Priority-based risk explanation
- Security-focused decision support

---

## Cloud Incident Copilot
### Status
Planned

### Summary
Incident analysis concept for turning logs, alerts, and events into likely causes, impact summaries, and next-step recommendations.

### Tags
- Incident Response
- Logs
- Alerts
- Analysis
- AWS

### Key points
- Alert and event summarization
- Likely-cause guidance
- Response-step recommendations

---

## 13) Detail pane design rules

### Desired feel
- premium
- calm
- technical
- architectural
- readable
- intentional

### Structure rules
- strong title hierarchy
- one concise summary
- labeled sections
- controlled pill usage
- cleaner CTA alignment
- no giant walls of text

### Avoid
- giant stacks of pills
- generic card/component look
- too many same-size buttons
- overlong paragraphs
- too many equal-weight sections

---

## 14) Styling direction for the selected project area

### What it should feel like
- project explorer panel
- architecture briefing surface
- selected system detail area

### What it should not feel like
- generic popup
- modal card
- template marketing box

### Styling rules
- dark premium surface
- restrained border treatment
- mild geometry if desired, but not game-like
- cleaner than the early angular “HUD” concept
- integrated into the page layout

---

## 15) Node map styling rules

### Background
- dark navy / charcoal
- subtle grid or structure only
- minimal noise
- no busy texture-heavy concept-art background

### Connection lines
- thin
- intentional
- soft glow only when necessary
- selected route may brighten slightly
- **As built:** stroke-width 1.5; opacity — Live 0.35, In Build 0.28, Planned 0.18, selected 0.82

### Node surfaces
- compact and readable
- not too decorative
- easy to scan
- strong status indication without looking like app store tiles

---

## 16) Motion and interaction

### Good motion
- subtle node highlight on hover
- selected node emphasis
- smooth content swap in detail panel
- gentle fade/slide transitions
- nothing flashy

### Avoid
- pulse spam
- sweeping HUD animations
- rapid line flashes
- anything that feels like a game menu

---

## 17) Content tone

The whole page should read as:
- advanced
- cloud-native
- engineered
- thoughtful
- premium

It should avoid sounding:
- overhyped
- too startup-marketing
- too sci-fi
- too buzzword-heavy

---

## 18) Why this concept is stronger than the old purple grid

### The old purple page
- clearer in a traditional portfolio sense
- but more generic
- felt like a project-card page many people could have

### This new concept
- more systems-engineering aligned
- more memorable
- more architecture-driven
- more cloud-native
- more visually distinctive without needing gimmicks

### Final judgment
This concept is the better direction as long as execution stays restrained.

---

## 19) Build guidance for Claude

When implementing this page:

- keep the AWS node-web concept
- build the page as an interactive project map, not a project-card grid
- use a center AWS hub with surrounding projects
- keep the design clean and enterprise-like
- avoid game/HUD/cyberpunk styling
- make node labels accurate and consistent
- keep the right-side detail pane readable and structured
- use the locked status and button logic
- treat the page as a polished real portfolio page, not a concept art exercise

### Important implementation priorities
1. Accurate node layout and labels
2. Clean node interactions
3. Stable right-side detail-pane updates
4. Calm visual styling
5. Clear hierarchy and readable copy

### Not implemented (intentionally dropped)
- Edit/upload controls visible in early mockups — not built, not needed for V1 portfolio page

---

## 20) Final locked decisions

- Advanced Projects page is a separate doc from Linux Ops
- the purple card-grid concept is replaced by the AWS node-web concept
- AWS stays in the center as the shared platform hub
- project nodes remain around the hub
- clicking a node updates the selected-project detail surface
- detail area stays persistent on the right
- live / in-build / planned states use different treatment
- background and styling must stay restrained and non-game-like
- this page should feel like a cloud architecture explorer, not a dashboard gimmick
- **Default selected node on load:** RAG Knowledge Chatbot
- **Mobile breakpoint:** 768px — radial map hidden, stacked `#mobile-list` shown below detail pane
- **Planned node opacity:** 0.58 / color `#4b5563`
- **Connection line opacities:** Live 0.35, In Build 0.28, Planned 0.18, selected 0.82 / stroke-width 1.5
- **Radial layout implementation:** absolute-positioned HTML `.node` divs inside a `position: relative` container; SVG overlay draws lines via `getBoundingClientRect()`, redrawn on click and window resize

---

## 21) Modal styling conventions

### Labels and dashes
- Section headers (`.modal-label`) and bullet dashes use `var(--dim)` → `#64748b`
- No purple in modal content — all label/dash color is grey

### Panel border
- `.modal-panel` border: `1px solid var(--border)` → `#30363d`
- No purple border (`#4a2d8c` was removed)

### Dead CSS variables — do not reintroduce
The following variables existed in the old purple card grid and were removed in the redesign:
- `--card-bg`
- `--card-border`
- `--card-hover-bg`
- `--badge-bg`
- `--badge-text`
