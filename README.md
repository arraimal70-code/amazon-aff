# Nexora Commerce AI

Nexora Commerce AI is an Amazon-style affiliate marketing storefront plus an admin-only AI operations command center.

## Main goal

Sell Amazon affiliate products through product discovery, reviews, best-product rankings, comparison pages, buying guides, safe outbound Amazon purchase buttons, and admin-side execution management.

## Customer-facing features

- Storefront home page
- Featured products
- Product review pages
- Best Products page
- Product comparison engine
- Blog and buying guides
- Product search tracking
- Product interaction tracking
- Safe outbound redirect tracking so raw affiliate URLs are not shown to visitors

## Admin-only features

- Google sign-in backend endpoint
- Local development admin login
- Admin-only Employees section hidden from standard users
- CEO instruction panel
- CEO delegation to HR, Sales, Coding, Bug Solver, and Executive teams
- Direct task assignment to individual executives or employees
- Task board
- CEO/team reports
- User activity tracking
- Affiliate click tracking
- Search query tracking
- Product interaction tracking

## Reporting hierarchy

- Admin instructs CEO
- CEO reports to Admin
- HR reports to CEO
- Employees report to HR and Executive
- Executive reviews analytics, sales movement, and execution quality

## Google login setup

Set these environment variables in production:

```bash
GOOGLE_CLIENT_ID=your-google-client-id
JWT_SECRET=replace-with-strong-secret
ADMIN_EMAILS=your-admin-email@gmail.com
```

The frontend currently includes a local development admin login button. For production Google sign-in, connect Google Identity Services on the frontend and post the returned credential to:

```text
POST /api/auth/google
```

## Run locally

```bash
npm run install:all
npm run dev
```

Open:

```text
http://localhost:5173
```

Admin:

```text
http://localhost:5173/#admin
```

Important pages:

```text
/#best
/#compare
/#ai
/#admin
```

## Important note about purchases

Amazon does not automatically send exact customer purchase data to your custom website. This app tracks clicks, searches, product views, comparisons, and outbound intent. Exact purchase and commission data must be imported or reconciled from Amazon Associates reports.