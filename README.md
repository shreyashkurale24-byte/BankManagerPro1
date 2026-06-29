# 🗄 BANK Manager — Full CRUD UI for 36 Tables

A beautiful, animated Flask web application for managing your MySQL/SQLite database.

## Features
- ✅ **All 36 tables** auto-detected from your SQL dump
- ✅ **Create / Read / Update / Delete** for every table
- ✅ **Search** across text columns with live filtering
- ✅ **Pagination** (15 rows per page)
- ✅ **Schema browser** — see all columns, types, PKs
- ✅ **Dark futuristic UI** with smooth animations
- ✅ **Delete confirmation modal** (no accidental deletes)
- ✅ **Sidebar table navigator** with quick-search

## Quick Start

### Step 1 — Install Flask
```bash
pip install flask
```

### Step 2 — Place your SQL file
Make sure `Dumptables.sql` is in the same folder as `app.py`.

### Step 3 — Run
```bash
python3 run.py
```

### Step 4 — Open Browser
Navigate to: **http://127.0.0.1:5000**

---

## Connecting to a Real MySQL Database

To connect to a live MySQL database instead of SQLite:

1. Install `PyMySQL`:
   ```bash
   pip install pymysql
   ```
2. In `app.py`, replace the `get_db()` function:
   ```python
   import pymysql
   
   def get_db():
       return pymysql.connect(
           host="127.0.0.1",
           user="root",
           password="your_password",
           database="testdata",
           cursorclass=pymysql.cursors.DictCursor
       )
   ```

---

## Tables Included

| Table | Description |
|-------|-------------|
| airlimit | AIR transaction limits |
| atmcard | ATM card master |
| atmcardrequest | ATM card requests |
| atmtrn | ATM transactions |
| bnkmstremit | Bank master for remittance |
| brbegin | Branch begin/day-open details |
| brholidays | Branch holiday master |
| brncmst | Branch master |
| cagentcode | Pigmy agent code generation |
| cashbal | Cash opening/closing balance |
| cashlimit | Cash limits |
| chartofac | Standard chart of accounts |
| chqbchrg | Cheque book charges |
| chqissue | Cheque issue |
| cimsalm | CIMS ALM statements |
| cimsbasic | Statutory financial statements |
| cimsfields | CIMS fields definition |
| counterdevice | Counter device mapping |
| excelmast | Excel ETL master |
| goldrate | Gold rates |
| groupinstr | Group standing instructions |
| groupinstrexec | Group instruction executions |
| grpcoll | Group collections |
| ... (36 total) | |

---

## File Structure

```
db_manager/
├── app.py           ← Main Flask application
├── run.py           ← Startup script
├── Dumptables.sql   ← Your SQL schema
├── data.db          ← SQLite database (auto-created)
├── README.md        ← This file
└── templates/
    ├── base.html    ← Sidebar + layout
    ├── index.html   ← Dashboard
    ├── table.html   ← Table view with grid
    └── form.html    ← Create / Edit form
```
