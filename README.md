# Streamlit CRM — Clients & Action Points Dashboard

A modern Streamlit app for managing **clients** and **action points** with analytics and exports.
Designed to run locally or on **Streamlit Community Cloud**.

## Quick Start (Local)

```bash
cd streamlit_crm_dashboard
pip install -r requirements.txt
streamlit run app.py
```

The app will create (or use) a local `crm.db` SQLite database. You can load sample data via the sidebar button.

## Deploy to Streamlit Community Cloud

1. Push this folder to a GitHub repo (e.g., `streamlit-crm-dashboard`).
2. On https://share.streamlit.io, create a new app:
   - **Repository**: your GitHub repo
   - **Branch**: main
   - **Main file path**: `app.py`
3. Add environment variable (optional):
   - `CRM_DB_PATH` (default is `crm.db` in the app root).
4. Click **Deploy**.

### Note on PyInstaller

Streamlit apps are typically **not** packaged with PyInstaller for the cloud.
Instead, deploy directly as a Streamlit project (this repo) with `requirements.txt`.

If you still need a one-file desktop binary for local distribution, you can try:
```bash
pyinstaller --noconfirm --onefile --console   --add-data "crm.db;."   --hidden-import=streamlit   --collect-all streamlit   app.py
```
But this is separate from Streamlit Cloud hosting.

## Features

- CRUD for **Clients** and **Action Points**
- Sidebar **Filters** (status, priority, assignee, client, dates)
- **KPI** cards
- **Waterfall** ("stair-like") chart for statuses
- **Pareto** chart for action points by client
- **Timeline** (Gantt-style) of created→due
- **Grouped bar** analytics by priority per client
- **Excel export** of filtered action points

## Project Structure

```
.
├── app.py
├── crm.db
├── requirements.txt
├── README.md
├── .streamlit/
│   └── config.toml
└── assets/
    └── logo.png
```

## Theming

You can adjust UI colors in `.streamlit/config.toml`.

---

© 2025 Streamlit CRM Demo
