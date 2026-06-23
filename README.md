# imdb-sql-analysis
SQL analysis of IMDB movie data to guide RSVP Movies' global release strategy — 29 queries using MySQL Window Functions, CTEs, and Joins
# 🎬 IMDB SQL Analysis — RSVP Movies Case Study

## 📌 Project Overview

RSVP Movies, an Indian production company, is planning a global release in 2022. This project analyzes **three years of IMDB movie data** using advanced SQL to deliver data-driven recommendations on genre selection, director/actor partnerships, and production strategy for an international audience.

This was completed as part of the **PwC Academy Business Analytics & Consulting Program (UpGrad)**.

---

## 🎯 Business Objective

Help RSVP Movies answer:
- Which genres should they focus on for a global release?
- Which directors and actors have the highest audience ratings?
- Which production houses make the best collaboration partners?
- What is the market landscape for Drama, Action, and Thriller globally?

---

## 🗂️ Dataset

| Table | Description | Rows |
|---|---|---|
| `movie` | Movie metadata — title, year, country, gross income | 7,997 |
| `ratings` | Avg rating, total votes, median rating | 7,997 |
| `genre` | Genre tags per movie | 14,662 |
| `director_mapping` | Movie–director relationships | 3,867 |
| `role_mapping` | Movie–actor/actress relationships | 15,615 |
| `names` | Person info — directors, actors | 25,735 |

**Source:** IMDB (2017–2019)

---

## 🛠️ Tools & Concepts Used

- **MySQL** — DDL, DML, Joins, Subqueries
- **Window Functions** — `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()`, `SUM() OVER()`
- **CTEs** — `WITH` clause for readable multi-step logic
- **Aggregate Functions** — `COUNT()`, `AVG()`, `SUM()`, `MIN()`, `MAX()`
- **Date Functions** — `MONTH()`, `YEAR()`, filtering by date ranges

---

## 📊 Key Business Questions Answered (29 Queries)

### Segment 1 — Movie & Genre Analysis
- Total rows per table; NULL value audit
- Movies released per year and month-wise trend
- India & USA output in 2019
- Genre with highest movie count → **Drama dominates**
- Average duration per genre

### Segment 2 — Ratings Analysis
- Top 10 movies by average rating
- Production houses with most hit movies (avg rating > 8)
- German vs Italian movies — vote comparison
- Movies starting with "The" with avg rating > 8

### Segment 3 — Director & Actor Analysis
- Top 3 directors in each of the top 3 genres (avg rating > 8)
- Top 2 actors with median rating ≥ 8
- Top 3 production houses by total votes received
- Top actresses in Hindi movies in India

### Segment 4 — Advanced Analytics
- Genre-wise running total & moving average of duration
- Top 5 highest-grossing movies per year per genre (Window Functions)
- Top 3 actresses in Drama with Super Hit movies (avg > 8)

---

## 💡 Key Findings & Recommendations

| # | Finding | Recommendation |
|---|---|---|
| 1 | **Drama** is the highest-producing genre (4,285 movies) | Target Drama as the primary genre |
| 2 | **Action & Thriller** rank in top 3 by volume | Consider a Drama-Thriller blend |
| 3 | **Dream Warrior Pictures & National Theatre Live** top production houses by hit rate | Prioritize as co-production partners |
| 4 | **Star Cinema & Twentieth Century Fox** lead on vote counts | Strong global distribution network |
| 5 | Top-rated directors (avg > 8) come from multilingual productions | Cast internationally recognized talent |

---

## 📁 Repository Structure

```
imdb-sql-analysis/
│
├── IMDB_dataset_import.sql     # Database creation & full data import
├── IMDB_question.sql           # Assignment questions (29 queries)
├── IMDB_Solution.sql           # Complete answered SQL script
├── IMDb-movies-Data-and-ERD.xlsx  # Dataset + Entity Relationship Diagram
└── README.md                   # Project documentation (this file)
```

---

## ▶️ How to Run

1. Open **MySQL Workbench** (or any MySQL client)
2. Run `IMDB_dataset_import.sql` to create and populate the database
3. Open `IMDB_Solution.sql` and execute queries segment by segment
4. Refer to `IMDB_question.sql` to see the original problem statements

```sql
-- Quick start
USE imdb;
SELECT * FROM movie LIMIT 5;
```

---

## 🧠 Skills Demonstrated

- Complex multi-table JOINs across 6 tables
- Business-context SQL — translating analyst questions into queries
- Window functions for ranking and running totals
- NULL handling and data quality checks
- Structured problem-solving using the STAR framework

---

## 👤 Author

**Jebaz Jeeva M**  
PGDM — Business Analytics & Marketing | Rajalakshmi School of Business  
[LinkedIn](www.linkedin.com/in/jebazjeeva) | [GitHub](https://github.com/JebazJeeva)
