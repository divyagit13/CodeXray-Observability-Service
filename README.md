# CodeXray-Observability-Service
Setup & Installation
# 1. Clone the repository
git clone https://github.com/<your-username>/CodeXray-Observability-Service.git
cd CodeXray-Observability-Service

# 2. (Optional) Create virtual environment
python -m venv venv
source venv/bin/activate       # on Linux/Mac
venv\Scripts\activate          # on Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the Flask app
python app.py


App runs at 👉 http://127.0.0.1:5000

🔍 Project Summary

CodeXray is a Python-based microservice that monitors system health (CPU & Memory), generates alerts when thresholds are breached, and exposes secure REST APIs for reporting.
It also provides a web dashboard for real-time metric visualization and configuration.

⚙️ Tech Stack
Component	Technology	Purpose
Language	Python	Simple, efficient, rich ecosystem
Framework	Flask	Lightweight REST microframework
Database	SQLite	Fast, file-based database
System Metrics	psutil	Cross-platform CPU & memory monitoring
Security	Werkzeug (Flask)	Password hashing & token-based sessions
Frontend	HTML, Chart.js, JS	Visualizes metrics and alerts
Styling	Custom CSS	Clean and responsive dashboard design
🧠 Architecture Overview
+-------------------+
| Dashboard (HTML/JS)|
+---------+---------+
          |
          | REST API (token-secured)
          v
+-------------------+
| Flask App (app.py)|
| /register, /login |
| /collect-metrics  |
| /summary, /config |
+---------+---------+
          |
          v
+-------------------+
| SQLite (metrics,  |
| alerts, config)   |
+---------+---------+
          ^
          |
+-------------------+
| psutil (CPU, Mem) |
+-------------------+

🧪 Functional Flow

Register / Login

/api/register → create user

/api/login → returns session_token

Collect Metrics

/api/collect-metrics → records CPU & memory usage, generates alerts

View Summary

/api/summary → total alerts, breakdown, averages

Dashboard

Open /dashboard in browser

Paste your session token

Click “Refresh Now” to view live metrics and alerts

📊 Key Features

Secure authentication (hashed passwords + session tokens)

Real-time CPU & memory monitoring

Alert storage with timestamps

Configurable alert thresholds (via UI or API)

Interactive dashboard built with Chart.js

💡 Why This Stack

Flask + SQLite + psutil → lightweight, portable, and efficient

Ideal for demonstrating observability concepts & secure coding

Easy to extend with:

PostgreSQL or MongoDB

JWT authentication

Background job scheduler (Celery)

🎥 Demo Guide (For Submission)

Start the Flask app in VS Code terminal.

Use Postman to show:

/register, /login, /collect-metrics, /summary

Open /dashboard and paste session token.

Show:

Graph updating every 10s

Alerts appearing when thresholds are breached

Updating thresholds via UI

📁 Folder Structure
CodeXray/
├── app.py
├── metrics.py
├── db.py
├── log_analyzer.py
├── requirements.txt
├── templates/
│   └── dashboard.html
├── static/
│   ├── css/style.css
│   └── js/dashboard.js
└── data/sample.log
