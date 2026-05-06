# Advanced Projects

A single-page catalog of advanced AWS + AI portfolio projects, rendered as an interactive node graph with status badges and per-project architecture modals.

**Live demo:** https://d2uisqfxjzeo6a.cloudfront.net

## Overview

This page is the index for the AWS-heavy half of the portfolio at [jimmyhubbard2.cc](https://jimmyhubbard2.cc) — a catalog of advanced projects with status indicators (Live / Planned) and per-project architecture modals. The desktop view renders the catalog as a node graph; mobile falls back to a name-list. Each Live node links to the project's CloudFront demo and opens an in-page modal describing the linked project's architecture. The catalog itself is a single static `index.html` — every architecture story it tells lives in the linked project repo, not here.

## Projects indexed

**Live:**
- **RAG Knowledge Chatbot** — RAG chatbot answering questions about the author's background and AWS Well-Architected Framework guidance, with custom retrieval over chunked documents and Titan embeddings.
- **FieldIQ** — college football analytics dashboard with multiple compute views across all 164 FBS programs.
- **Linux Ops Command Copilot** — plain-English-to-Bash translator with risk classification and safer-alternative suggestions.

**Planned:**
- **AI Security Assessment Agent** — scoped, queued for build.
- **Cloud Incident Copilot** — scoped, queued for build.

## Tech stack

| Layer | Technology |
|---|---|
| Markup / style / logic | Vanilla HTML5, CSS3, JavaScript |
| Hosting | AWS S3 + CloudFront |

No npm, no bundler, no framework. Single static file.

## Local development

```bash
python3 -m http.server 8080
```

Open `http://localhost:8080`. No build step, no dependencies to install.

## Deployment

Deploys automatically on push to `main` via GitHub Actions ([`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)). The workflow uploads `index.html` to S3 with the correct `Content-Type` and invalidates the CloudFront distribution.

**S3 bucket:** `jimmy-advanced-projects` (us-east-1)  
**CloudFront distribution:** `E1VZ0ELKDC3LN0`

## Project structure

```
advanced-projects/
└── index.html      # Complete catalog page — HTML, CSS, JS, and project data in one file
```

## License

MIT — see [LICENSE](LICENSE)

## Author

Jimmy Hubbard — [github.com/jhubb88](https://github.com/jhubb88)

---

*Part of [jhubb88's portfolio](https://jimmyhubbard2.cc)*
