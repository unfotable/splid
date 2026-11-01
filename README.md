<div align="center">

# SPLID

### Smart, simple expense splitting for shared trips.

[![GitHub Repo](https://img.shields.io/badge/REPO-unfotable%2Fsplid-000000?style=for-the-badge&logo=github&logoColor=00FF66)](https://github.com/unfotable/splid)
[![Status](https://img.shields.io/badge/SYSTEM-ONLINE-000000?style=for-the-badge&labelColor=0a0a0a&color=00FF66)]()
[![UI Theme](https://img.shields.io/badge/THEME-MONOSPACE_CLI-000000?style=for-the-badge&labelColor=0a0a0a&color=FFB000)]()

**Track shared costs. See who owes whom. Settle up without the spreadsheet.**

</div>

<p align="center">

</p>

---

## `01 // OVERVIEW`

SPLID (shown in the app as **Hisaab**) is a lightweight, browser-based expense splitter for trips, outings, and shared groups. Add people, record who paid, choose how each expense should be divided, and get a clear picture of everyone's balance.

Instead of manually calculating repayments, SPLID works out the outstanding balances and can simplify them into a smaller set of payments.

## `02 // FEATURES`

- **Group management** — create groups, rename them, and manage members.
- **Expense tracking** — record an expense, its payer, date, description, and category.
- **Flexible splits** — divide costs equally, by custom amounts, or by percentage.
- **Balance overview** — see who owes whom and inspect the outstanding amounts.
- **Simplified settlements** — calculate a reduced set of repayments to settle group balances.
- **Settlement history** — record full or partial repayments and update balances.
- **Categories** — organize expenses such as Food, Travel, Stay, and Miscellaneous.
- **Guided demo** — explore the sample trip before entering your own expenses.
- **Local persistence** — your data is saved in the browser using `localStorage`; no account is required.

## `03 // LIVE DEMO`

Try the hosted app:

**[Open SPLID](https://splid.unfo.workers.dev/)**

The app opens with sample data so you can explore the workflow. Start a fresh group when you're ready to use your own data.

## `04 // RUN LOCALLY`

SPLID is a static web app. There is no build step or package installation required.

```bash
# Clone the repository
git clone https://github.com/unfotable/splid.git

# Enter the project directory
cd splid

# Start a local static server
python -m http.server 8000
```

Open **http://localhost:8000** in your browser.

You can also open `index.html` directly, but using a local server is recommended for a consistent browser experience.

## `05 // HOW TO USE`

1. **Create a group** — give your trip or shared activity a name.
2. **Add members** — enter the people sharing the expenses.
3. **Log an expense** — add a description, amount, category, and payer.
4. **Choose a split** — select Equal, Custom, or Percentage and assign each person's share.
5. **Review balances** — check the balance view to see outstanding debts.
6. **Simplify payments** — use the simplified view to see a reduced settlement plan.
7. **Record repayments** — add a settlement when someone pays back their share.

## `06 // TECH STACK`

| Layer | Technology |
|---|---|
| UI | HTML, CSS, JavaScript |
| UI rendering | React 18 |
| JSX-like templating | HTM |
| Styling | Tailwind CSS (CDN) |
| Data persistence | Browser `localStorage` |
| Additional browser libraries | SheetJS, ExcelJS, MQTT.js |

The app loads its front-end libraries from CDNs and runs directly in the browser.

## `07 // PROJECT STRUCTURE`

```text
splid/
├── index.html          # Main app interface and client-side application
├── app.js              # Application script in the repository
├── styles.css          # Stylesheet
├── logo_s.svg          # Logo asset
├── Splid.apk           # Android package
└── Splid v9.apk        # Android package
```

## `08 // DATA & PRIVACY`

- Group and expense data is stored locally in the browser that you use.
- The app does not require an account to use its browser-based workflow.
- Browser-local data is not automatically synchronized between devices or browsers.
- Clearing the browser's site data may remove locally stored app data. Export or back up anything important before clearing it.

## `09 // CONTRIBUTING`

Suggestions, bug reports, and improvements are welcome.

- [Open an issue](https://github.com/unfotable/splid/issues)
- [Browse the source](https://github.com/unfotable/splid)

For code changes, fork the repository, create a focused branch, and submit a pull request with a clear description of the change.

## `10 // LICENSE`

No license information was confirmed while preparing this README. Check the repository for a `LICENSE` file before reusing or redistributing the project.

---

<div align="center">

**SPLID — shared expenses, clearer balances.**

<sub>Built for trips, groups, and the people splitting the bill.</sub>

</div>
