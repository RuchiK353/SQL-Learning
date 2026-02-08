# 📊 SQL Learning Journey

> Documenting my path from zero to Data Analyst

![Progress](https://img.shields.io/badge/Days%20Completed-3%2F270-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-green)
![Streak](https://img.shields.io/badge/Streak-2%20days-red)

---

## Day 3 - Advanced Filtering (February 8, 2026)

### What I Learned:
- Combining conditions with AND, OR, NOT
- Using parentheses to control logic order
- IN operator for multiple values
- NOT IN to exclude multiple values
- DISTINCT to find unique values
- COUNT with DISTINCT for unique counts

### Queries I Wrote Today:

```sql
-- Combining AND conditions
SELECT * FROM movies 
WHERE year > 2000 AND rating > 8;

-- Using OR for alternatives
SELECT * FROM movies 
WHERE year < 1990 OR year > 2010;

-- NOT to exclude
SELECT * FROM movies 
WHERE NOT director = 'John Lasseter';

-- Complex logic with parentheses
SELECT * FROM movies 
WHERE (year > 2000 OR rating > 8) 
AND director IN ('Pixar', 'Disney');

-- IN operator (cleaner than multiple ORs)
SELECT * FROM movies 
WHERE director IN ('Pixar', 'Disney', 'DreamWorks');

-- NOT IN to exclude multiple
SELECT * FROM movies 
WHERE year NOT IN (2005, 2010, 2015);

-- HackerRank: Count unique vs total
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) FROM STATION;

-- HackerRank: Filter cities starting with vowels
SELECT DISTINCT CITY FROM STATION 
WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' 
   OR CITY LIKE 'I%' OR CITY LIKE 'O%' 
   OR CITY LIKE 'U%';

-- Alternative using IN (cleaner)
SELECT DISTINCT CITY FROM STATION 
WHERE LEFT(CITY, 1) IN ('A','E','I','O','U');
```

### Key Takeaways:
1. AND requires BOTH conditions to be true
2. OR requires AT LEAST ONE condition to be true
3. Use parentheses () to control order of operations
4. IN is cleaner than multiple OR statements
5. DISTINCT removes duplicate values
6. Can combine COUNT with DISTINCT to count unique values

### HackerRank Progress:
- Problems Solved Today: 5/5 ✅
- Total Problems Solved: 10
- Sections: Basic Select
- Success Rate: 100%
- New Concepts: DISTINCT, COUNT with DISTINCT, string functions

### Challenges Faced:
- Weather Observation Station 5 was tricky (ORDER BY + LIMIT for min/max)
- Understanding when to use AND vs OR
- Remembering to use DISTINCT when counting unique values

### Time Spent: 1 hour
### Exercises Completed: 
- SQLBolt Lesson 5 (review)
- HackerRank Basic Select (5 problems)
- IN operator practice (3 queries)

### Tomorrow's Goal:
- Learn aggregate functions (COUNT, SUM, AVG, MIN, MAX)
- Practice GROUP BY basics
- Solve 5 more HackerRank problems from "Aggregation" section

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
- ✅ Day 3 - Advanced Filtering (Feb 8, 2026)
- ⬜ Day 4 - Aggregate Functions
- ⬜ Day 5 - GROUP BY Practice
- ⬜ Day 6 - JOINs Introduction
- ⬜ Day 7 - Week Review

### Stats
- **Total Days Completed:** 3/270
- **Actual Days Elapsed:** 2 days
- **Current Streak:** 2 days 🔥🔥
- **Skills Acquired:** SELECT, WHERE, ORDER BY, LIMIT, AND, OR, NOT, IN, DISTINCT
- **HackerRank Problems Solved:** 10
- **Total Exercises Completed:** 24+
- **Next Milestone:** Complete Week 1 (Day 7)

---

## 🎯 Learning Goals

**Short-term (Month 1):**
- ✅ Master SQL fundamentals (filtering ✓, sorting ✓)
- ⬜ Learn aggregate functions (next up!)
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

### Day 3:
- `AND` - both conditions must be true
- `OR` - at least one condition must be true
- `NOT` - negate a condition
- `IN` - match any value in a list
- `NOT IN` - exclude values in a list
- `DISTINCT` - remove duplicates
- `COUNT(DISTINCT column)` - count unique values
- Parentheses `()` for complex logic

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

**Day 3 Reflection (February 8, 2026):**
- What went well: IN operator clicked immediately, HackerRank getting easier
- What was challenging: Complex WHERE logic with multiple conditions
- Energy level: 8/10
- Confidence level: 8/10
- Favorite moment: Solving Weather Observation Station 4 (felt like a puzzle!)
- Tomorrow's excitement: Ready to learn aggregate functions!

**Day 2 Reflection (February 7, 2026):**
- Completed with Day 1 for strong start

**Day 1 Reflection (February 7, 2026):**
- What went well: Completed 2 lessons! Strong momentum established
- What was challenging: Staying focused for 2 hours
- Energy level: 9/10
- Confidence level: 8/10
- Feeling: Excited and motivated!

---

## 🏆 Achievements Unlocked
- ✅ 3-day concept mastery (SELECT, WHERE, ORDER BY, AND/OR/NOT, IN)
- ✅ 10 HackerRank problems solved
- ✅ 2-day learning streak maintained
- ✅ Advanced filtering skills acquired
- ✅ Portfolio consistently updated

---

## 📈 Learning Insights

**Patterns I'm Noticing:**
1. SQL problems are like puzzles - breaking them into steps helps
2. Reading the question 2-3 times prevents mistakes
3. IN operator saves so much typing vs multiple ORs
4. DISTINCT is crucial for "unique" questions
5. HackerRank discussions are gold when stuck

**Study Habits Working Well:**
- 1 hour daily is sustainable
- Documenting immediately helps retention
- HackerRank for practice > just reading tutorials
- Taking screenshots of solutions for future reference

---

*Last updated: February 8, 2026*
*Consistency streak: 2 days | Target completion: October 2026*
