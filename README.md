# REVX — Revenue Intelligence Dashboard

A self-contained, single-file sales analytics dashboard. No build step, no install, no dependencies to manage. Drop `index.html` into a repo and it works.

🔗 **[Live Demo](https://kumarsinghujjwal29-bit.github.io/Sales_dashboard/)** 

---

## Features

- **4 KPI cards** — Total Revenue, Units Sold, Avg Unit Price, Top Product with H1 vs H2 growth indicator
- **Revenue Trend** — area chart showing monthly revenue across the year
- **Category Mix** — donut chart breaking down revenue share by product category
- **Top Products** — horizontal bar chart ranked by revenue
- **Regional Performance** — bar chart with per-territory summary cards
- **Data Table** — sortable by any column, paginated at 10 rows
- **Filters** — click-to-toggle pills for Category and Region; all charts update instantly
- **File Import** — drag & drop or click to import your own CSV or Excel file
- **Smart column detection** — recognises common column name variations automatically

---

## Getting Started

### Deploy to GitHub Pages (3 steps)

1. Create a new GitHub repo
2. Upload `index.html` via *Add file → Upload files*
3. Go to *Settings → Pages*, set source to `main` branch / root, click *Save*

Your dashboard will be live at `https://YOUR_USERNAME.github.io/REPO_NAME` within about a minute.

### Run locally

No server needed. Just open `index.html` directly in any modern browser:

```
double-click index.html
```

Or via a local server if you prefer:

```bash
npx serve .
# or
python3 -m http.server
```

---

## Importing Your Own Data

Click **↑ Import CSV / Excel** in the top-right, or drag and drop a file anywhere on the page. Supports `.csv`, `.xlsx`, and `.xls`.

### Column names

The dashboard auto-detects your columns. It looks for these names (case-insensitive):

| Data field | Recognised column names |
|---|---|
| Date / Period | `date`, `month`, `period` |
| Product | `product`, `item`, `name`, `sku` |
| Category | `category`, `cat`, `type`, `segment`, `department` |
| Region | `region`, `area`, `territory`, `zone`, `location` |
| Units | `units`, `quantity`, `qty`, `count`, `sold` |
| Revenue | `revenue`, `sales`, `amount`, `total`, `value`, `income` |

You don't need all columns — the dashboard will work with whatever it finds.

### Example CSV structure

```csv
date,product,category,region,units,revenue
2024-01,Laptop Pro,Electronics,North,42,52458
2024-01,Wireless Earbuds,Electronics,South,88,13112
2024-02,Trail Runners,Apparel,East,65,7670
```

---


## Tech Stack

Everything loads from public CDNs — no `package.json`, no `node_modules`.

| Library | Version | Purpose |
|---|---|---|
| [React](https://react.dev) | 18.2.0 | UI framework |
| [Recharts](https://recharts.org) | 2.10.3 | Charts |
| [PapaParse](https://www.papaparse.com) | 5.4.1 | CSV parsing |
| [SheetJS](https://sheetjs.com) | 0.18.5 | Excel parsing |
| [Babel Standalone](https://babeljs.io) | 7.23.2 | JSX → JS in-browser |

---

## Project Structure

```
/
├── index.html           # The entire dashboard (single file)
└── README.md
```

---

## Customisation

All styling lives in the `C` theme object near the top of the `<script>` block in `index.html`. Change colours, add products to `PRODUCTS`, or swap in your own default dataset by replacing the `SAMPLE` variable.

```js
const C = {
  accent: "#f0a922",  // ← change the gold to any colour you like
  ...
};
```

---

## License

© 2026 Ujjwal Kumar Singh. All rights reserved.

This project and its source code may not be copied, modified, or redistributed without explicit permission from the author.
