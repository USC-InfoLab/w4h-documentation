---
id: 7e1e6339-bb0f-46e2-826e-f9fc6b49dfae
slug: w4h-app-setup-for-developers
title: W4H-app Setup for Developers
card_title: ''
description: ''
action_label: Open
doc_type: internal
sort_order: 0
hidden: false
updated_at: '2026-04-13T16:26:03.005261'
is_feature_card: false
show_in_docs: true
toc:
- id: w4h-app-setup-for-developers
  level: 2
  title: W4H-app Setup for Developers
- id: system-architecture
  level: 3
  title: System architecture
- id: first-time-setup-workflow
  level: 3
  title: First-time setup workflow
- id: w4h-app-setup
  level: 3
  title: w4h-app Setup
- id: recommended-ide-setup
  level: 4
  title: Recommended IDE Setup
- id: recommended-browser-setup
  level: 4
  title: Recommended Browser Setup
- id: customize-configuration
  level: 4
  title: Customize configuration
- id: project-setup
  level: 4
  title: Project Setup
- id: compile-and-hot-reload-for-development
  level: 4
  title: Compile and Hot-Reload for Development
- id: compile-and-minify-for-production
  level: 4
  title: Compile and Minify for Production
- id: run-end-to-end-tests-with-playwright-https-playwright-dev-
  level: 4
  title: Run End-to-End Tests with [Playwright](https://playwright.dev)
- id: lint-with-eslint-https-eslint-org-
  level: 4
  title: Lint with [ESLint](https://eslint.org/)
card_order: 0
---

# W4H-app Setup for Developers

## System architecture

```mermaid
flowchart TB
  subgraph Clients
    U[User / browser]
  end

  subgraph w4h_app["w4h-app (frontend)"]
    V[Vue 3 + Vite SPA]
  end

  subgraph w4h_api["w4h-api (backend)"]
    E[Express HTTP API]
  end

  subgraph Data
    DB[(PostgreSQL)]
  end

  subgraph Optional
    Mail[SMTP / email]
  end

  U --> V
  V -->|"HTTPS/HTTP (VITE_API_URL)"| E
  E --> DB
  E -.-> Mail
```

**Summary:** The browser loads the SPA. The SPA talks only to the API (via `VITE_API_URL`). The API owns database access and optional outbound email.

---

## First-time setup workflow

Until the API and database are configured, the UI may guide you through database connection and admin creation (handled by **w4h-api** endpoints, not by direct DB access from the browser):

```mermaid
flowchart LR
  A[Install deps & set VITE_API_URL] --> B[Start w4h-api]
  B --> C[Start w4h-app dev server]
  C --> D[Open app in browser]
  D --> E{API + DB ready?}
  E -->|No DB yet| F[DB setup via UI → API]
  F --> G[Admin account → API]
  G --> H[Login]
  E -->|Already configured| H
  H --> I[Use app]
```

---

## w4h-app Setup

This template should help get you started developing with Vue 3 in Vite.

### Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

### Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

### Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

### Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Run End-to-End Tests with [Playwright](https://playwright.dev)

```sh
# Install browsers for the first run
npx playwright install

# When testing on CI, must build the project first
npm run build

# Runs the end-to-end tests
npm run test:e2e
# Runs the tests only on Chromium
npm run test:e2e -- --project=chromium
# Runs the tests of a specific file
npm run test:e2e -- tests/example.spec.ts
# Runs the tests in debug mode
npm run test:e2e -- --debug
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
