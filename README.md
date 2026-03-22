# Spendly - Personal Finance Tracker

A simple, intuitive expense tracking web application built with Flask. Track your expenses, understand spending patterns, and take control of your financial life — one transaction at a time.

![Spendly](https://img.shields.io/badge/Spendly-Track%20Every%20Rupee-blue)

## Features

- **Log Expenses Instantly** - Add any expense in seconds with category, amount, date, and description
- **Understand Spending Patterns** - See exactly where your money goes with category breakdowns and monthly summaries
- **Filter by Time Period** - View spending for any date range — last week, last month, or custom periods
- **User Authentication** - Secure registration and login system
- **Clean, Modern UI** - Beautiful, responsive design with intuitive navigation

## Tech Stack

- **Backend**: Python 3.x with Flask 3.1.3
- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Database**: SQLite (planned)
- **Testing**: pytest 8.3.5 with pytest-flask

## Project Structure

```
expense-tracker/
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── database/
│   ├── __init__.py    # Database package init
│   └── db.py          # Database utilities (to be implemented)
├── static/
│   ├── css/
│   │   └── style.css  # Application styles
│   └── js/
│   │   └── main.js    # Frontend JavaScript
├── templates/
│   ├── base.html      # Base template with navbar and footer
│   ├── landing.html   # Landing/home page
│   ├── register.html  # User registration page
│   └── login.html     # User login page
└── venv/              # Virtual environment (not tracked in git)
```

## Installation & Setup

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd expense-tracker
```

### Step 2: Create Virtual Environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run the Application

```bash
python app.py
```

The app will start on `http://localhost:5001`

## Current Implementation Status

### Completed Routes

| Route | Description | Status |
|-------|-------------|--------|
| `GET /` | Landing page | ✅ Complete |
| `GET /register` | Registration page | ✅ Complete |
| `GET /login` | Login page | ✅ Complete |

### Placeholder Routes (To Be Implemented)

| Route | Description | Step |
|-------|-------------|------|
| `GET /logout` | User logout | Step 3 |
| `GET /profile` | User profile page | Step 4 |
| `GET /expenses/add` | Add new expense form | Step 7 |
| `GET /expenses/<id>/edit` | Edit expense form | Step 8 |
| `GET /expenses/<id>/delete` | Delete expense | Step 9 |

## Development Roadmap

The following features are planned for implementation:

1. **Database Setup** - Implement `get_db()`, `init_db()`, and `seed_db()` in `database/db.py`
2. **User Authentication** - Complete registration, login, and logout functionality
3. **User Profiles** - Create profile management pages
4. **Expense Management** - Add, edit, and delete expense functionality
5. **Dashboard & Analytics** - Spending summaries, category breakdowns, date filtering

## Database Schema (Planned)

```sql
-- Users table
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    email TEXT UNIQUE NOT NULL,
    password_hash TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Expenses table
CREATE TABLE expenses (
    id INTEGER PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    amount REAL NOT NULL,
    category TEXT NOT NULL,
    description TEXT,
    date DATE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Running Tests

```bash
pytest
```

## Contributing

This is a learning project. Follow the step-by-step roadmap to implement features.

## License

MIT License

---

**Spendly** - Track every rupee. Own your finances.
