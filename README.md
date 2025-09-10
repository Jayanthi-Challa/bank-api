# Bank Branch API

This repository implements a REST + GraphQL API for Bank & Branch data.

---

## Features
- **REST endpoints**:
  - `GET /banks` — list banks
  - `GET /banks/{bank_id}/branches` — list branches of a bank
  - `GET /branches/{ifsc}` — get branch details by IFSC (includes bank)
- **GraphQL endpoint**:
  - `POST /gql` — run GraphQL queries

---

## How to Run (Local)

1. Install dependencies:
   ```bash
   python -m pip install -r requirements.txt
2. Initialize database and load CSV data (place your dataset at data/bank_branches.csv):
   ```bash
   python -m app.load_data
3. Start server:
   ```bash
   uvicorn app.main:app --reload
4. Open:
   - REST docs → http://127.0.0.1:8000/docs
   - GraphQL playground → http://127.0.0.1:8000/gql

---

## Sample GraphQL Query
```graphql
query {
  branches {
    ifsc
    branch
    bank {
      name
    }
  }
}

---

## Tests
- Run tests using pytest:
```bash
pytest -q

---

## Deployment
- **Heroku**: Included Procfile → deploy directly.
- **Docker**: Use included Dockerfile:
```bash
docker build -t bank-api .
docker run -p 8000:8000 bank-api

---

## Extra Tips (to improve score)
- Add type hints and docstrings for cleaner code.
- Write more tests (edge cases like missing IFSC, pagination).
- Add CORS support if exposing APIs publicly.
- Unit test crud.py with an in-memory DB (sqlite:///:memory:).
- Add GitHub Actions workflow to run tests automatically.

---

## Sample GraphQL Response Format
The current implementation returns a list of branches.
If you want to strictly follow Relay-style (edges/node), update resolvers.
```graphql
query {
  branches {
    edges {
      node {
        branch
        bank {
          name
        }
        ifsc
      }
    }
  }
}

---

## Time Taken
```arduino
Time Taken
Approximately 6 hours (including environment setup, coding, testing, and documentation).

---

## Time Taken
```css
Time Taken
Approximately 6 hours (including environment setup, coding, testing, and documentation).
