# Expense Tracker

## Setup Instructions

1. Clone the repository:

   ```bash
   git clone https://github.com/Emonemon74/expense-tracker.git
   cd expense-tracker
   ```

2. Copy the environment template:

   ```bash
   cp .env.example .env
   ```

3. Update `.env`:

   ```env
   SUPER_SECRET_KEY=change-me
   DATABASE_URL=sqlite:///expenses.db
   ```

   For PostgreSQL, use:

   ```env
   DATABASE_URL=postgresql+psycopg://postgres:postgres@localhost:5432/expenses_tracker
   ```

4. Install dependencies:

   ```bash
   uv sync
   ```

5. Create the database tables:

   ```bash
   uv run python -c "from app import app, db; app.app_context().push(); db.create_all()"
   ```

6. Start the app:

   ```bash
   uv run python app.py
   ```

7. Open:

   ```text
   http://localhost:5000
   ```
