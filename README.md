<div align="center">

# `SPLID`
### **S**equential **P**ayload & **I**ndividual **D**ispatcher

[![GitHub Repo](https://img.shields.io/badge/REPO-unfotable%2Fsplid-000000?style=for-the-badge&logo=github&logoColor=00FF66)](https://github.com/unfotable/splid)
[![Status](https://img.shields.io/badge/SYSTEM-ONLINE-000000?style=for-the-badge&labelColor=0a0a0a&color=00FF66)]()
[![UI Theme](https://img.shields.io/badge/THEME-MONOSPACE_CLI-000000?style=for-the-badge&labelColor=0a0a0a&color=FFB000)]()

<p align="center">
  <b>A terminal-inspired web utility for splitting bulk email payloads into throttled, one-by-one individual dispatches from a single SMTP source—complete with live execution logs and persistent transmission history.</b>
</p>

[Report Bug](https://github.com/unfotable/splid/issues) · [Request Feature](https://github.com/unfotable/splid/issues)

</div>

---

## `01 // OVERVIEW`

**SPLID** (*Split Dispatch*) solves the problem of traditional bulk emailing (where BCCing gets flagged as spam and external SaaS tools are overkill). 

Wrapped in a distraction-free, **100% monospace developer UI**, SPLID takes a single message payload and a list of recipients, then dispatches emails **sequentially one at a time** from your own email account with customizable time-throttling, dynamic variable injection, real-time terminal feedback, and local history persistence.

```text
+-------------------+       +------------------------+       +-------------------------+
|  SINGLE SENDER    |       |     SPLID ENGINE       |       |  INDIVIDUAL RECIPIENTS  |
|  (SMTP Account)   | ----> |  - Syntax Validation   | ----> |  [01] userA@domain.com  |
|                   |       |  - Variable Injection  |  3s   |  [02] userB@domain.com  |
|  + Message Body   |       |  - Throttled Queue     | delay |  [03] userC@domain.com  |
|  + CSV / Raw List |       |  - Local History Log   |       |  [..] ...               |
+-------------------+       +------------------------+       +-------------------------+
02 // CORE FEATURES
[SEQUENTIAL_DISPATCH]: Sends emails individually one-by-one rather than mass BCC, ensuring high deliverability and inbox placement.
[THROTTLE_CONTROL]: Configurable delay interval (e.g., 2s – 15s between dispatches) to bypass SMTP rate limits and spam filters.
[DYNAMIC_VARIABLES]: Inject personalized placeholders like {{name}}, {{company}}, or {{custom_id}} into subjects and message bodies.
[RECIPIENT_PARSER]: Paste raw comma/newline-separated emails or upload .CSV files. Automatically strips duplicates and flags invalid syntax.
[LIVE_TERMINAL_LOGS]: Watch real-time execution statuses ([200 OK], [RETRY], [ERR_TIMEOUT]) with millisecond timestamps as your queue processes.
[TRANSMISSION_HISTORY]: Automatically saves every campaign batch to local storage (localStorage / IndexedDB). Inspect past payloads, view success/fail ratios, export logs to .JSON/.CSV, or re-run failed dispatches with one click.
[TECHNICAL_MONO_UI]: Built with a high-contrast dark palette (#0a0a0a), sharp 1px borders, exposed grids, and strictly monospace typography (JetBrains Mono / Fira Code).
03 // TECH STACK
Layer	Technology	Purpose
Frontend	React / Next.js / Vite	UI state management, queue controller, history viewer
Styling	Tailwind CSS	Brutalist grid system, dark terminal theme, monospace typography
Backend / API	Node.js & Express	Lightweight local/serverless relay for SMTP transport
Mail Engine	Nodemailer	Direct SMTP authentication and sequential dispatching
Storage	LocalStorage / IndexedDB	Zero-database client-side transmission history & log caching
04 // INSTALLATION & SETUP
Clone the repository and spin up the local development environment:

Bash

# 1. Clone the repository
git clone https://github.com/unfotable/splid.git

# 2. Navigate into the project directory
cd splid

# 3. Install dependencies
npm install

# 4. Start the development server
npm run dev
Once running, open your browser and navigate to:

text

http://localhost:3000
05 // SMTP CONFIGURATION GUIDE
To dispatch emails from your own account (e.g., Gmail, Outlook, or custom domain), configure the SMTP Panel inside the app:

Host: smtp.gmail.com (or your provider's SMTP server)
Port: 465 (SSL) or 587 (TLS)
User: your-email@domain.com
Password: Your App Password (Note: For Gmail/Outlook, generate an App-Specific Password in your account security settings rather than using your regular login password).
06 // USAGE WORKFLOW
[CONFIG]: Enter your SMTP credentials in the top/side configuration module and verify status shows SMTP: READY.
[INGEST]: Paste your recipient email list or upload a .CSV file. Click [VALIDATE_LIST] to clean duplicates.
[COMPOSE]: Write your Subject and Body (Markdown or Raw HTML). Use {{variable}} tags if mapping from a CSV.
[THROTTLE]: Set the delay slider (recommended: 3s - 5s per email).
[EXECUTE]: Hit [ EXECUTE DISPATCH ] and monitor the live console output.
[ARCHIVE]: Switch to the [HISTORY_LOGS] tab at any time to review past batches, export reports, or retry failed addresses.
07 // PROJECT STRUCTURE
text

splid/
├── src/
│   ├── components/
│   │   ├── SmtpConfig.jsx       # SMTP credential inputs & connection status
│   │   ├── RecipientInput.jsx   # CSV uploader, parser, and validator
│   │   ├── Composer.jsx         # Monospace editor with live preview
│   │   ├── TerminalLog.jsx      # Real-time scrolling execution console
│   │   └── HistoryPanel.jsx     # Saved logs, payload inspector, & JSON export
│   ├── utils/
│   │   ├── queueEngine.js       # Sequential async loop & delay throttling
│   │   └── storage.js           # LocalStorage history CRUD operations
│   └── App.jsx
├── server/
│   └── index.js                 # Node/Nodemailer SMTP relay endpoint
├── package.json
└── README.md
