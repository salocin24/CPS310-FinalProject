# CPS 310 Final Project
## Recipe & Meal Planner

A command-line Recipe & Meal Planner built in Python, extended from the CPS 310 starter project.

## Features

### Starter features
- Load recipe data and configuration from JSON
- List all recipes
- Search recipes by name
- Filter recipes by category
- View recipe details

### New features
| Feature | Category | Status |
| --- | --- | --- |
| Search by Ingredient | Recipe Management | Complete |
| Random Meal Suggestion | Meal Planning | Complete |
| Scale Recipes by Servings | Grocery / Calculations | Planned |

- **Search by Ingredient**: enter an ingredient to find every recipe that uses it. Case-insensitive, and partial matches work ("chicken" finds "chicken breast").
- **Random Meal Suggestion**: get a randomly selected recipe from the collection, with its full details.

## Setup

### Windows
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python app.py
```

### macOS / Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r requirements.txt
python3 app.py
```

## Run Tests

### Windows
```powershell
python -m pytest -v
```

### macOS / Linux
```bash
python3 -m pytest -v
```

## Continuous Integration
GitHub Actions (`.github/workflows/tests.yml`) runs the full pytest suite automatically on every pull request and push to `master`.

## Development Workflow
Planned work is tracked in GitHub Issues. Each feature is built on its own branch, merged through a pull request after tests pass, and linked to its Issue.