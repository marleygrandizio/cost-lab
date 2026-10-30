# Mission 3 — Pricing & Cost Laboratory

A browser-only, responsive pricing and cost model for the unnamed concert-streaming venture described in Mission 1. It preserves the distinction between published cost references and student-controlled assumptions. The first offer is one hypothetical single-concert pass; subscription plans and additional offers can be added as student scenarios.

## Run locally

Serve this folder over HTTP (the dashboard loads its bundled JSON-formatted data files with `fetch`):

```sh
python3 -m http.server 8000
```

Open `http://localhost:8000/` when the command is run inside this directory.

## Model behavior

- Financial calculations run in the browser. There is no backend, login, database, paid API, or required development server after static deployment.
- A local browser copy persists with `localStorage`. Use **Export working model** to back it up; importing replaces the current local working copy.
- One-time setup cash is separate from monthly operating cost. Capitalized startup lines enter the simplified monthly break-even view only when amortization/depreciation is enabled with a useful life.
- Monthly and annual subscription revenue and per-transaction costs are normalized to a monthly view. Multiple offer break-even uses the currently entered monthly sales mix and allocates shared overhead once.
- Expected sales quantities are student scenarios, not forecasts. Cost and risk outputs are conditional arithmetic, not predictions of demand or business failure.
- The student must evaluate, write a justification, acknowledge displayed warnings, and confirm manually. Nothing is auto-confirmed.
- After confirmation, both downloadable reports are generated from the same immutable snapshot. The Word document is assembled as a real OOXML `.docx` ZIP package in the browser; the companion JSON contains internal model data separately from customer-facing offer fields.

## Evidence and assumptions

Official source references and check dates are bundled in `data/cost_model.txt`. Stripe's published US online-card fee and AWS IVS usage prices are researched references. BLS May 2025 wage medians are employee-wage references, not contractor quotes. Hours, event audience allocation, rights shares, production budgets, marketing, insurance, and legal budgets are marked estimated or illustrative. No generic music rights rate is asserted.

The imported Mission 1 competitive dataset is stored separately at `data/competitor_data.txt` and retains the October 27, 2026 research snapshot. Competitor prices may have changed.

## Venture website fields

The setup provides `https://github.com/marleygrandizio/pricing-dashboard.git` as the original repository URL. That repository is Mission 2's competitive research dashboard. Mission 3 does not provide a separate live venture website URL, so the application and report clearly identify it as not supplied rather than treating the research dashboard as the commercial venture website.

## GitHub Pages

`.github/workflows/pages.yml` publishes this static repository root to GitHub Pages on pushes to `main`. No Vite build or repository-path rewrite is needed; CSS, JavaScript, and local JSON use relative paths.
