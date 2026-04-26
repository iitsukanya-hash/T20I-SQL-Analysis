# 🏏 T20I Cricket SQL Analysis Project

## 📌 Overview

This project contains SQL queries to analyze T20 International cricket matches dataset (2024).
It includes insights such as head-to-head records, win percentage, ranking, and performance by ground.

---

## 📂 Database Structure

The dataset includes:

* Team1
* Team2
* Winner
* Margin
* MatchDate
* Ground

---

## 🔍 Key Questions Solved

### 1️⃣ Matches between specific teams

Find matches played between two teams in 2024.

### 2️⃣ Team with highest wins

Identify the team with maximum wins.

### 3️⃣ Ranking teams by wins

Use window functions to rank teams.

### 4️⃣ Highest average winning margin

Calculate average margin (runs).

### 5️⃣ Matches above average margin

Find matches where margin > average.

### 6️⃣ Most wins while chasing

Identify teams winning by wickets.

### 7️⃣ Head-to-head record

Compare wins between two teams.

### 8️⃣ Month with most matches

Find busiest month in 2024.

### 9️⃣ Win percentage of each team

Calculate:

* Matches played
* Wins
* Win %

### 🔟 Best team at each ground

Use `RANK()` to find top team per ground.

---

## 🧠 Concepts Used

* UNION ALL
* GROUP BY
* Aggregate functions (COUNT, SUM, AVG)
* Conditional aggregation
* Window functions (RANK)
* String functions (SUBSTRING, LOCATE)
* Date functions (YEAR, MONTHNAME)

---

## 💡 Example Query (Win Percentage)

```sql
SELECT Team,count(*) as matches,
sum(Team=Winner) as wins,
round(100*sum(Team=Winner)/count(*),2) as percentage_win 
FROM (
    SELECT Team1 as Team,Winner,MatchDate FROM T20I
    UNION ALL 
    SELECT Team2 as Team,Winner,MatchDate FROM T20I
) t
WHERE YEAR(MatchDate)=2024
GROUP BY Team;
```

---

## 📊 Dataset

The dataset is manually created and inserted using SQL.

---

## 🚀 How to Run

1. Create database
2. Run table creation query
3. Insert data
4. Execute analysis queries

---

## 📌 Author
Sukanya Saha
Data Science Learner
