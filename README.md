# Agency Manager

A self-contained admin dashboard for a marketing/agency business — no build step, no backend, no server required. Open `index.html` in a browser and it runs.

## Getting started

Just open `index.html` directly, or serve the folder with any static file server, e.g.:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Demo login

This is a **client-side demo login only** — not real authentication, and not meant for production use.

- Username: `admin`
- Password: `admin123`

## What it does

- **Employees** — name, CNIC number (auto-formatted), photo, employee ID, designation, salary.
- **Clients** — client name, business name, platforms included, category, monthly retainer.
- **Payments** — record a payment per client per month, mark it Cleared or Pending. Only cleared payments count as revenue.
- **Expenses** — office expenses by category; deducted from the account balance.
- **Investments** — owner cash injections; added to the account balance.
- **Dashboard** — revenue vs. expenses chart (last 6 months), expense breakdown chart, and key stats (revenue, expenses, investments, net balance, MRR, pending payments).

## Data storage

All data is stored in the browser's `localStorage` (per-browser, per-device — nothing is sent to a server). On first login the app seeds a few sample records so the dashboard isn't empty; use **Reset Demo Data** on the dashboard to wipe and reseed at any time.

## Notes for turning this into a real product

This is a demo/prototype. Before using it for real business data you'd want:
- Real authentication (not a hardcoded password) and a backend/database instead of `localStorage`.
- Server-side storage for employee photos instead of embedding them as base64.
- Multi-user access control if more than one admin needs to log in.
