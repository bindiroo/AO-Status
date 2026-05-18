# AO Status Report

A self-contained HTML dashboard for tracking advance order (AO) performance across seasons. No server, no dependencies to install — just open the HTML file in a browser.

## Files

| File | Purpose |
|------|---------|
| `AO-Status-Report.html` | The dashboard (open this in a browser) |
| `AO-Status.csv` | Weekly data export — replace this each week to update the report |

## Weekly Update Workflow

1. Export your updated AO data as `AO-Status.csv`
2. Open `AO-Status-Report.html` in a browser
3. Drag and drop the new CSV file anywhere onto the page — all charts and KPIs update instantly
4. Or click **Load CSV** in the top-right corner to browse for the file

## What's in the Dashboard

**KPI Cards**
- Current season (Summer 2026) units and revenue vs. the prior year at the same point in the season
- Fall 2025 totals vs. Fall 2024
- All-time units and revenue across every season

**Fall Seasons tab** — compares Fall 2024 vs. Fall 2025
**Summer Seasons tab** — compares Summer 2024, Summer 2025, and Summer 2026

Each tab includes:
- **Cumulative Units** — week-normalized trend lines (Week 1 = first week of orders for that season, so years are directly comparable)
- **Cumulative Revenue** — same view for dollars
- **Monthly Activity** — new units booked per month, side-by-side by season

**Season Summary Table** — totals, avg $/unit, weeks active, units/week, and YoY % for every season

## CSV Format

The dashboard expects a CSV with these columns:

```
Season, Date, Units, Amount, Source
SUMMER 2026, 5/1/26, 54, $882.00, AO
```

- **Season** — must match one of: `FALL 2024`, `FALL 2025`, `SUMMER 2024`, `SUMMER 2025`, `SUMMER 2026`
- **Date** — M/D/YY format
- **Units** — integer
- **Amount** — dollar value (commas and `$` sign are fine)
- Summary/total rows (blank Date) are automatically ignored

## Sharing with the Team

**Option A — Shared drive:** Put both files in a shared folder. Teammates open the HTML file locally and drag in the latest CSV themselves.

**Option B — GitHub Pages:** Enable GitHub Pages on this repo and link teammates to the URL. They'll need to upload a new CSV to the repo each week to update the hosted version.

**Option C — Local web server:** Run `python3 -m http.server` in this folder, then open `http://localhost:8000/AO-Status-Report.html`. The dashboard will auto-load `AO-Status.csv` from the same directory on every page refresh — no drag-and-drop needed.
