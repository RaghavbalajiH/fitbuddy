# FitBuddy – AI Fitness Plan Generator

A complete FastAPI + Jinja2 + SQLite + Gemini implementation based on the supplied FitBuddy project document.

## Features
- Personalized 7-day workout plan
- Nutrition/recovery tip
- Feedback-based plan update
- SQLite + SQLAlchemy persistence
- Original/updated plan history
- All-users admin-style view
- FastAPI `/docs`
- Current `google-genai` SDK and configurable model IDs

## Windows / VS Code

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and add your Gemini API key.

Run:

```powershell
python -m uvicorn app.main:app --reload
```

Open `http://127.0.0.1:8000`.

API docs: `http://127.0.0.1:8000/docs`

## Model configuration
The original document names Gemini 1.5 Pro and Gemini Flash. Model availability changes over time, so this implementation keeps the same architecture (strong model for workout/update and fast model for nutrition) while putting model IDs in `.env`. Change them there if needed.

## Project tree

```text
FitBuddyAI/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── routes.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   ├── config.py
│   └── ai/
│       ├── __init__.py
│       ├── gemini_generator.py
│       ├── gemini_flash_generator.py
│       └── updated_plan.py
├── templates/
├── static/
├── requirements.txt
├── .env.example
├── .gitignore
├── run_windows.bat
└── README.md
```
