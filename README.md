# Home Inventory

An offline-first household cash, shopping, inventory and daily-expense tracker — a single-page Progressive Web App built with vanilla HTML, CSS and JavaScript (no frameworks, no backend). All data lives on-device in **IndexedDB**.

## Features

- **Dashboard** — live cash balance, today's expense/shopping/transport, open sessions, recent activity
- **Cash & Denominations** — Bangladeshi Taka note/coin counter with auto-calculated totals, optional advanced note metadata (condition, torn/chhera, serial), and saved cash snapshots
- **Shopping Sessions** — quick free-text item entry ("Rice, 1090"), advanced shop/item/bill fields, journey/transport tracking, and end-of-session reconciliation with a clear discrepancy warning
- **Expenses & Income** — daily expense logging and income entries, both category-tagged
- **Hierarchical Categories** — unlimited category/subcategory nesting with **English + Bengali names**, case-insensitive duplicate detection across the whole tree (so re-adding an existing category never creates a duplicate), and breadcrumb display everywhere a category is shown or picked
- **Inventory** — stock levels with low-stock alerts, auto-updated from marked shopping purchases
- **Reports** — daily, monthly, shopping and cash summaries with lightweight bar charts
- **Transactions** — searchable, filterable, sortable ledger; every transaction can be edited or deleted
- **Export / Import**
  - Full JSON backup & restore (every store)
  - Excel (.xlsx, via SheetJS) export/import scoped to **Categories, Expenses and Sessions** (plus SessionItems/SessionJourneys sheets)
  - Multi-file CSV export/import for the same three tables
  - All merge paths match by ID + `updatedAt` (newest wins) and never duplicate a category
- **Bilingual UI** — English / বাংলা toggle
- **Offline-first** — installable PWA, service-worker cached, works after the first load with no internet connection

## Run it

Just open `index.html` in a modern browser. For full PWA install + offline service-worker behavior, serve the folder over `http://localhost` or host it on GitHub Pages.

```bash
# any static server works, e.g.
npx serve .
```

## Known limitations

- Session line-items and journeys are stored inside each session record rather than as fully separate normalized tables
- CSV session export does not include item/journey line detail (use Excel or the full JSON backup for that)
- No cloud sync — export/import is the supported way to move data between devices

## Author

**MD IKRAMUL ISLAM SIDDIQUE POROSH** (Porosh)
- 📞 +8801672896992
- ▶️ YouTube: https://www.youtube.com/@mdikramulsilamsiddiqueporosh
- 📘 Facebook: https://facebook.com/iamrjporosh
- 🐦 Twitter: https://twitter.com/rjporosh
- 🌐 Portfolio: https://rjporosh.github.io
