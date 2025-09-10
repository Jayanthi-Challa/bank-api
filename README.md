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
