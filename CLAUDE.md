# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A reveal.js presentation on observability practices, built with AsciiDoc and compiled to HTML. The presentation covers three real-world case studies (REXs — Retours d'Expérience) on observability implementations.

## Commands

**Development (recommended via Docker):**
```bash
docker compose run --rm node npm i   # Install dependencies
docker compose up -d                  # Start watch mode (auto-rebuild on changes)
```

**Direct Node.js:**
```bash
npm install
npm run build   # One-time build → dist/index.html
npm run watch   # Watch *.js, *.adoc, *.css and auto-rebuild
```

The build script is `asciidoctor-revealjs.js` — it converts AsciiDoc to reveal.js HTML and copies assets/styles to `dist/`.

## Architecture

**Build pipeline:**
```
*.adoc source files
    ↓ asciidoctor-revealjs.js
dist/index.html (standalone presentation + bundled reveal.js + assets)
```

**Content structure — modular page includes from `index.adoc`:**
- `pages/start.adoc` — speaker intro
- `pages/rexs.adoc` — overview of the three REXs
- `pages/rex1-general-monitoring.adoc` — main content (most complete)
- `pages/rex2-elk.adoc`, `pages/rex3-uniformation-control-center.adoc`, `pages/synthesis.adoc`, `pages/end.adoc` — stubs in progress

**Reveal.js configuration** lives in the header of `index.adoc` (theme, progress, history, timing, custom CSS path).

**Custom styles:** `styles/yannschepens/stylesheets/style.css` — copied to `dist/styles/` at build time.

**Assets:** `assets/default/images/` — architectural diagrams (PNG), copied to `dist/assets/` at build time.

## Content Status

REX 1 content is complete. REX 2, REX 3, synthesis, and end pages are stubs awaiting content.

REX 1 covers a logging architecture for a software forge: Filebeat + Docker GELF → Logstash → Elasticsearch → Kibana/Grafana, handling ~120 log types at several GiB/day.