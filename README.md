# Nexora Commerce AI

Nexora Commerce AI is an Amazon-style affiliate marketing storefront plus a functional admin-only affiliate operations platform.

## Main goal

Sell Amazon affiliate products through product discovery, reviews, best-product rankings, comparison pages, buying guides, safe outbound Amazon purchase buttons, user-intent tracking, and admin-side team execution.

## Customer-facing features

- Storefront home page
- Clean Featured vs Search Results separation
- Product review pages
- Best Products page
- Product comparison engine with Best Value, Best Overall, and Budget Pick
- Blog and buying guides
- Standard user account/history page
- Search tracking
- Product view tracking
- Review click tracking
- Compare tracking
- Amazon outbound click / purchase-intent tracking through `/out/:productId`

## Admin-only features

- Google sign-in endpoint using Google Identity Services
- Role-based users: `admin` or `user`
- Admin role determined by `ADMIN_EMAILS`
- Protected admin APIs and protected admin routes
- Admin tabs: Overview, Employees, CEO Instructions, Task Board, Reports, Activity, Users
- Employee add/edit/delete/status/workload/report management
- CEO instruction workflow
- Automatic task delegation to Sales, HR, Executive, Coding, Social, Outreach, and Bug Solver teams
- Direct instructions to any employee or executive
- Dynamic task board
- Task completion requires result text
- Completed tasks create employee reports
- CEO final report generated when delegated tasks are completed
- Social queue
- DM/outreach queue
- Full activity log
- Per-user timeline

## Reporting hierarchy

- Admin instructs CEO
- CEO reports to Admin
- HR reports to CEO
- Employees report to HR and Executive
- Executive reviews analytics, sales movement, and execution quality

## Google login setup

Set these environment variables:

```bash
GOOGLE_CLIENT_ID=your-google-client-id
JWT_SECRET=replace-with-strong-secret
ADMIN_EMAILS=your-admin-email@gmail.com
```

Frontend Google button uses:

```bash
VITE_GOOGLE_CLIENT_ID=your-google-client-id
```

For local testing, the app includes Admin Google Demo and Standard User Google Demo buttons. Production should use the real Google button.

## Run locally

```bash
npm run install:all
npm run dev
```

Open:

```text
http://localhost:5173
```

Routes:

```text
/#/
/#/best
/#/compare
/#/blog
/#/account
/#/admin
/#/admin/employees
/#/admin/instructions
/#/admin/tasks
/#/admin/reports
/#/admin/activity
/#/admin/users
```

## Acceptance test map

- Guest cannot access admin: admin route shows login.
- Standard user cannot see admin tools: nav hides admin, route shows access denied.
- Admin can instruct CEO: `/admin/instructions` creates instruction, delegated tasks, and report.
- Task Board updates: `/admin/tasks` reads persisted backend tasks.
- Completing tasks requires result text and creates reports.
- CEO final report is created when all tasks for an instruction are completed.
- Amazon buttons open tracked outbound links through `/out/:productId`.
- Product reviews open real product review pages.
- Activity log shows real user actions.
- Users page shows per-user timeline.
- Refreshing does not lose data because the backend stores everything in SQLite.

## Important note about Amazon purchases

Amazon does not automatically send exact customer purchase data to your custom website. This app tracks clicks, searches, product views, comparisons, and outbound purchase intent. Exact purchase and commission data must be imported or reconciled from Amazon Associates reports.