# Nexus TMS — Streamlit web edition

This folder contains a browser-based starter for the Traffic Management project. It keeps the original desktop program separate: `start_project.py` uses Tkinter and cannot run as a browser app. The Streamlit edition provides corridor overview, map, traffic history, alerts, and a basic route comparison view.

## Run locally on Windows

Open PowerShell in this folder and run:

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m streamlit run streamlit_app.py
```

If PowerShell blocks activation, use the environment's executable directly:

```powershell
py -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe -m streamlit run streamlit_app.py
```

The app creates `traffic_control.db` beside `streamlit_app.py` on first launch and seeds sample Delhi traffic data. To use an existing compatible `traffic_control.db`, place it in this folder before launching. Do not copy `traffic_control.db-journal`; SQLite creates and manages journal files as needed.

## Deploy on Streamlit Community Cloud

1. Create a GitHub repository and upload the contents of this folder.
2. In [Streamlit Community Cloud](https://share.streamlit.io/), choose **Create app**.
3. Select your repository and branch, and set the app file to `streamlit_app.py`.
4. Deploy. Community Cloud installs the packages listed in `requirements.txt`.

The current web edition uses the included simulated/demo data. TomTom live telemetry and the original desktop controls have not been ported into this Streamlit starter. Add any future API credentials through Streamlit's app secrets; never commit keys to GitHub.
