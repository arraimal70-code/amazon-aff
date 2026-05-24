# Amazon Affiliate Operations App

A complete Amazon-style affiliate marketing store and operations app.

## Main goal

Sell Amazon affiliate products through product discovery, reviews, best-product rankings, comparison pages, buying guides, and safe outbound Amazon purchase buttons.

## Features

- Storefront home page
- Featured products
- Product review pages
- Best Products page
- Product comparison engine
- Category pages with filters and sorting
- Blog and buying guides
- Admin dashboard with demo password `admin123`
- Safe outbound redirect tracking so raw affiliate URLs are not shown to visitors
- AI Employees command center
- CEO, HR, employee, and executive reporting structure
- Admin reports and revenue goal tracking

## Reporting hierarchy

- CEO reports appear on the Admin page
- HR reports to CEO
- Employees report to HR and Executive
- Executive provides performance and growth summaries

## Run locally

```bash
npm install
npm run dev
```

Open:

```text
http://localhost:5173
```

Admin:

```text
http://localhost:5173/admin
Password: admin123
```

Important pages:

```text
/best-products
/compare
/ai-employees
/admin
```
