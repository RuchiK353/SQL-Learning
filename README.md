# 📊 SQL Learning Journey

> Documenting my path from zero to Data Analyst

## 🚀 Note: Strong Start!

Completed 2 lessons on Day 1 to build initial momentum. Future pace will be sustainable and consistent.

---

## Day 2 - Sorting & Filtering (February 7, 2026)

### What I Learned:
- ORDER BY clause for sorting results
- ASC (ascending) and DESC (descending) order
- LIMIT clause to restrict number of rows
- Sorting by multiple columns
- Query execution order matters

### Queries I Wrote Today:

```sql
-- Sort by year ascending (oldest first)
SELECT * FROM movies 
ORDER BY year ASC;

-- Sort by year descending (newest first)
SELECT * FROM movies 
ORDER BY year DESC;

-- Get top 5 newest movies
SELECT * FROM movies 
ORDER BY year DESC 
LIMIT 5;

-- Sort by multiple columns
SELECT title, year, rating FROM movies 
ORDER BY year DESC, rating DESC;

-- HackerRank: Cities with population > 100000
SELECT * FROM CITY 
WHERE COUNTRYCODE = 'USA' AND POPULATION > 100000;

-- HackerRank: Filter by specific criteria
SELECT NAME FROM CITY 
WHERE COUNTRYCODE = 'USA' AND POPULATION > 120000;
```

### Key Takeaways:
1. ORDER BY changes display order, not which rows are selected
2. Default sort is ascending (ASC) - can omit ASC keyword
3. DESC must be explicitly stated for descending order
4. LIMIT always comes at the END of the query
5. Can sort by multiple columns - first column is primary sort

### HackerRank Progress:
- Problems Solved: 5/5 ✅
- Section: Basic Select
- Success Rate: 100%
- Time Taken: ~30 minutes

### Time Spent: 1 hour
### Exercises Completed: 
- SQLBolt Lesson 4 (4 exercises)
- HackerRank Basic Select (5 problems)

---

## Day 1 - SQL Basics (February 7, 2026)

### What I Learned:
- SELECT statement - retrieves data from database
- FROM clause - specifies which table
- WHERE clause - filters data based on conditions
- Comparison operators: =, !=, <, >, <=, >=
- Logical operators: AND, OR
- Special operators: BETWEEN, IN, LIKE

### Queries I Wrote Today:

```sql
-- Get all columns from a table
SELECT * FROM movies;

-- Get specific columns
SELECT title, year FROM movies;

-- Filter with WHERE
SELECT * FROM movies WHERE year > 2000;

-- Multiple conditions
SELECT * FROM movies WHERE year BETWEEN 2000 AND 2010;

-- Pattern matching
SELECT title FROM movies WHERE title LIKE "Toy Story%";

-- Not equal
SELECT title FROM movies WHERE director != "John Lasseter";
```

### Key Takeaways:
1. SQL is not case-sensitive but UPPERCASE for keywords is convention
2. Every query needs SELECT and FROM
3. WHERE clause filters ROWS
4. Use semicolon ; to end queries
5. LIKE uses % as wildcard (any characters)

### Time Spent: 1 hour
### Exercises Completed: SQLBolt Lessons 1-3 (14 exercises)

---

## 📊 Progress Tracker

### Month 1: SQL Foundations
- ✅ Day 1 - SQL Basics (Feb 7, 2026)
- ✅ Day 2 - Sorting & Filtering (Feb 7, 2026)
- ⬜ Day 3 - Advanced Filtering
- ⬜ Day 4 - Aggregate Functions
- ⬜ Day 5 - GROUP BY Practice
- ⬜ Day 6 - Practice Day
- ⬜ Day 7 - Week Review

### Stats
- **Total Days Completed:** 2/270
- **Actual Days Elapsed:** 1 day
- **Current Streak:** 1 day 🔥
- **Skills Acquired:** SELECT, WHERE, ORDER BY, LIMIT, filtering, sorting
- **HackerRank Problems Solved:** 5
- **Total Exercises Completed:** 19
- **Next Milestone:** Complete Week 1 (Day 7)

---

## 🎯 Learning Goals

**Short-term (Month 1):**
- ✅ Master SQL fundamentals
- ⬜ Complete 3 SQL projects
- ⬜ Earn HackerRank SQL certification

**Long-term (9 months):**
- ⬜ Build complete data analyst portfolio
- ⬜ Master SQL, Excel, Power BI, Python
- ⬜ Land first Data Analyst job

---

## 🛠️ Tools & Resources

**Currently Using:**
- SQLBolt - Interactive SQL exercises
- HackerRank - Problem solving & certification prep
- SQLiteOnline - Practice environment
- Mode Analytics - SQL tutorials
- Alex The Analyst (YouTube) - Video lessons

**Tech Stack:**
- SQL (PostgreSQL/SQLite)
- GitHub (Portfolio & Documentation)

**Coming Soon:**
- Excel (Month 3)
- Power BI (Month 3-4)
- Python (Month 5-6)

---

## 📚 Concepts Mastered

### Day 2:
- `ORDER BY` - sort results
- `ASC` - ascending order (default)
- `DESC` - descending order
- `LIMIT` - restrict number of rows
- Multiple column sorting
- Query execution order

### Day 1:
- `SELECT` - retrieve data
- `FROM` - specify table
- `WHERE` - filter rows
- `=, !=, <, >, <=, >=` - comparison operators
- `BETWEEN` - range filtering
- `AND, OR` - logical operators
- `LIKE` - pattern matching
- `%` - wildcard character

---

## 💪 Daily Reflections

**Day 1 Reflection (February 7, 2026):**
- What went well: Completed 2 lessons! Strong momentum established
- What was challenging: Staying focused for 2 hours
- Energy level: 9/10
- Confidence level: 8/10
- Feeling: Excited and motivated!
- Tomorrow's plan: Back to 1 lesson/day for sustainability

---

## 🏆 Achievements Unlocked
- ✅ 2 lessons completed on Day 1 (strong start!)
- ✅ First HackerRank problems solved
- ✅ 19 total SQL exercises completed
- ✅ GitHub portfolio established
- ✅ Learning momentum activated

---

*Last updated: February 7, 2026*
*Target completion: October 2026 (9-month journey)*
