# Agency Manager

A self-contained admin dashboard for a marketing/agency business — no build step, no backend, no server required. Open `index.html` in a browser and it runs.

## Getting started

Just open `index.html` directly, or serve the folder with any static file server, e.g.:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Demo login

The login screen has two tabs, both **client-side demo logins only** — not real authentication, and not meant for production use.

**Admin**
- Username: `admin`
- Password: `admin123`

**Employee** (seeded demo account)
- Username: `ayesha.khan`
- Password: `employee123`

Every employee gets their own login username/password when they're registered by an admin (see Employees below).

## What it does

- **Employees** — name, CNIC number (auto-formatted), photo, employee ID, designation, salary, and a login username/password used for the employee's own portal.
- **Clients** — client name, business name, platforms included, category, monthly retainer.
- **Payments** — record a payment per client per month, mark it Cleared or Pending. Only cleared payments count as revenue.
- **Expenses** — office expenses by category; deducted from the account balance.
- **Investments** — owner cash injections; added to the account balance.
- **Dashboard** — revenue vs. expenses chart (last 6 months), expense breakdown chart, and key stats (revenue, expenses, investments, net balance, MRR, pending payments).
- **Attendance & employee portal** — when an employee signs in on the Employee tab, that login marks today's attendance and shows them their own profile and attendance history. Logging in by 9:15 AM counts as on-time; after 9:15 AM it's marked Late and Rs. 250 is deducted from that employee's salary for the month. Only the first login of the day counts. Admins see who's late today and each employee's running net salary for the month on the Employees page and the new Attendance page.

## Data storage

All data is stored in the browser's `localStorage` (per-browser, per-device — nothing is sent to a server). On first login the app seeds a few sample records so the dashboard isn't empty; use **Reset Demo Data** on the dashboard to wipe and reseed at any time.

## Notes for turning this into a real product

This is a demo/prototype. Before using it for real business data you'd want:
- Real authentication (not a hardcoded password) and a backend/database instead of `localStorage`.
- Server-side storage for employee photos instead of embedding them as base64.
- Multi-user access control if more than one admin needs to log in.
