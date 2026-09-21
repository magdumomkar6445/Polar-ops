# PolarOps — Polar Expedition Operations System

A self-contained prototype of a light, premium Arctic expedition command platform:
dashboard, personnel, cargo & logistics, assets, locations, emergency workflow,
reports, and an AI assistant demo. All demo data lives inside `public/index.html` —
no database or backend services required.

## Contents

```
server.js            Static file server (zero dependencies, Node.js only)
public/index.html    The complete PolarOps web app (single file)
README.md            This file
```

## Requirements

- Node.js 16 or newer (no npm packages to install)

## Getting started

1. Unzip the bundle and open a terminal in the extracted folder.
2. Start the server:

   ```bash
   node server.js
   ```

3. Open http://localhost:3000 in your browser.

You should see the PolarOps sign-in screen. Pick a role to enter the demo
(all data is simulated locally in the page).

## Configuration

| Variable | Default   | Purpose              |
| -------- | --------- | -------------------- |
| `PORT`   | `3000`    | Port to listen on    |
| `HOST`   | `0.0.0.0` | Interface to bind to |

Example:

```bash
PORT=8080 node server.js
```

## Health check

`GET /healthz` returns `{ "status": "ok", "app": "polarops", ... }` — useful when
running behind a reverse proxy or uptime monitor.

## Notes

- Unknown paths fall back to `index.html`, so the app works with any deep link.
- To stop the server, press `Ctrl+C`.
