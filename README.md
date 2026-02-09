# 📊 SQL Learning Journey

> Documenting my path from zero to Data Analyst

![Progress](https://img.shields.io/badge/Days%20Completed-4%2F270-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-green)
![Streak](https://img.shields.io/badge/Streak-4%20days-red)

---

## Day 4 - Aggregate Functions (February 10, 2026)

### What I Learned:
- COUNT() - count rows or values
- COUNT(DISTINCT) - count unique values
- SUM() - add up values
- AVG() - calculate average
- MIN() - find minimum value
- MAX() - find maximum value
- FLOOR() - round down
- CEIL() - round up
- Can combine aggregates with arithmetic

### Queries I Wrote Today:

```sql
-- Count cities with population > 100K
SELECT COUNT(*) 
FROM STATION 
WHERE POPULATION > 100000;

-- Total population in California
SELECT SUM(POPULATION) 
FROM STATION 
WHERE DISTRICT = 'California';

-- Average population (rounded down)
SELECT FLOOR(AVG(POPULATION)) 
FROM STATION;

-- Difference between max and min
SELECT MAX(POPULATION) - MIN(POPULATION) 
FROM CITY;

-- Count unique countries
SELECT COUNT(DISTINCT Country) 
FROM Customer;

-- Multiple aggregates in one query
SELECT 
    COUNT(*) as total_customers,
    AVG(age) as average_age,
    MIN(signup_date) as first_customer,
    MAX(total_spend) as highest_spender
FROM customers;
```

### Key Takeaways:
1. Aggregate functions collapse many rows into one result
2. COUNT(*) counts all rows, COUNT(column) ignores NULLs
3. COUNT(DISTINCT column) counts unique values only
4. Can combine aggregates with arithmetic (MAX - MIN)
5. FLOOR rounds down, CEIL rounds up, ROUND rounds to nearest
6. These functions answer real business questions!

### Business Applications Learned:
- **Total revenue:** `SUM(sales)`
- **Number of customers:** `COUNT(DISTINCT customer_id)`
- **Average order value:** `AVG(order_amount)`
- **Highest sale:** `MAX(sale_amount)`
- **Price range:** `MAX(price) - MIN(price)`
- **Product count:** `COUNT(*)`
- **Unique countries served:** `COUNT(DISTINCT country)`

### HackerRank Progress:
- Problems Solved Today: 5 ✅
- Total Problems Solved: 15+
- New Section: Aggregation
- Success Rate: 100%

### Challenges Faced:
- Understanding when to use COUNT(*) vs COUNT(column)
- Remembering FLOOR for "round down" vs ROUND
- Getting used to seeing many rows become one result

### Time Spent: 1 hour
### Exercises Completed: 
- 5 HackerRank Aggregation problems
- 6 practice queries on SQLiteOnline

### Tomorrow's Goal:
- Learn GROUP BY to combine aggregates with categories
- Answer "revenue by region" instead of just "total revenue"
- Unlock the full power of aggregate functions!

---

## Day 3 - Advanced Filtering (February 9, 2026)

### What I Learned:
- Combining conditions with AND, OR, NOT
- Using parentheses to control logic order
- IN operator for multiple values
- NOT IN to exclude multiple values
- DISTINCT to find unique values
- COUNT with DISTINCT for unique counts
- String functions (LEFT, LENGTH, SUBSTRING)
- Modulo operator (%) for even/odd

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
WHERE (year > 2000 OR director = 'Pixar') 
AND rating > 8;

-- IN operator (cleaner than multiple ORs)
SELECT * FROM movies 
WHERE director IN ('Pixar', 'Disney', 'DreamWorks');

-- NOT IN to exclude multiple
SELECT * FROM movies 
WHERE year NOT IN (2005, 2010, 2015);

-- HackerRank: Count unique vs total
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) 
FROM STATION;

-- HackerRank: Filter cities starting with vowels
SELECT DISTINCT CITY 
FROM STATION 
WHERE LEFT(CITY, 1) IN ('A','E','I','O','U');

-- HackerRank: Even ID numbers
SELECT DISTINCT CITY 
FROM STATION 
WHERE ID % 2 = 0;

-- HackerRank: Shortest and longest city names (UNION)
(SELECT CITY, LENGTH(CITY) 
 FROM STATION 
 ORDER BY LENGTH(CITY) ASC, CITY ASC 
 LIMIT 1)
UNION
(SELECT CITY, LENGTH(CITY) 
 FROM STATION 
 ORDER BY LENGTH(CITY) DESC, CITY ASC 
 LIMIT 1);
```

### Key Takeaways:
1. AND requires BOTH conditions to be true (narrows results)
2. OR requires AT LEAST ONE condition to be true (widens results)
3. Use parentheses () to control order of operations
4. IN is cleaner than multiple OR statements
5. DISTINCT removes duplicate values
6. Can combine COUNT with DISTINCT to count unique values
7. Modulo (%) operator useful for finding even/odd numbers

### HackerRank Progress:
- Problems Solved Today: 5/5 ✅
- Total Problems Solved: 10
- Section: Basic Select (Weather Observation Station problems)
- Success Rate: 100%
- Hardest Problem: Weather Observation Station 5 (UNION with LENGTH)

### Challenges Faced:
- Weather Observation Station 5 was tricky (needed UNION)
- Understanding when to use AND vs OR
- Remembering to use DISTINCT when counting unique values
- Parentheses placement in complex WHERE clauses

### Time Spent: 1 hour
### Exercises Completed: 
- SQLBolt Lesson 5 (review)
- HackerRank Basic Select (5 problems)
- String function practice (3 queries)

---

## Day 2 - Sorting & Filtering (February 8, 2026)

### What I Learned:
- ORDER BY clause for sorting results
- ASC (ascending) and DESC (descending) order
- LIMIT clause to restrict number of rows
- Sorting by multiple columns
- Query execution order matters
- OFFSET to skip rows

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

-- Skip first 5, get next 5
SELECT * FROM movies 
ORDER BY title ASC 
LIMIT 5 OFFSET 5;

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
6. OFFSET allows skipping rows (useful for pagination)

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
- ✅ Day 2 - Sorting & Filtering (Feb 8, 2026)
- ✅ Day 3 - Advanced Filtering (Feb 9, 2026)
- ✅ Day 4 - Aggregate Functions (Feb 10, 2026)
- ⬜ Day 5 - GROUP BY Practice
- ⬜ Day 6 - JOINs Introduction
- ⬜ Day 7 - Week Review

### Stats
- **Total Days Completed:** 4/270
- **Actual Days Elapsed:** 4 days
- **Current Streak:** 4 days 🔥🔥🔥🔥
- **Skills Acquired:** SELECT, WHERE, ORDER BY, LIMIT, AND, OR, NOT, IN, DISTINCT, COUNT, SUM, AVG, MIN, MAX
- **HackerRank Problems Solved:** 15+
- **Total Exercises Completed:** 33+
- **Next Milestone:** Complete Week 1 (Day 7)

---

## 🎯 Learning Goals

**Short-term (Month 1):**
- ✅ Master SQL fundamentals (filtering ✓, sorting ✓, aggregates ✓)
- ⬜ Learn GROUP BY (next up!)
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

### Day 4:
- `COUNT()` - count rows
- `COUNT(DISTINCT)` - count unique values
- `SUM()` - total/sum values
- `AVG()` - calculate average
- `MIN()` - find minimum
- `MAX()` - find maximum
- `FLOOR()` - round down
- `CEIL()` - round up
- `ROUND()` - round to nearest
- Combining aggregates with arithmetic

### Day 3:
- `AND` - both conditions must be true
- `OR` - at least one condition must be true
- `NOT` - negate a condition
- `IN` - match any value in a list
- `NOT IN` - exclude values in a list
- `DISTINCT` - remove duplicates
- `COUNT(DISTINCT column)` - count unique values
- `LEFT()` - get leftmost characters
- `LENGTH()` - string length
- `SUBSTRING()` - portion of string
- `%` (modulo) - remainder operator
- `UNION` - combine query results
- Parentheses `()` for complex logic

### Day 2:
- `ORDER BY` - sort results
- `ASC` - ascending order (default)
- `DESC` - descending order
- `LIMIT` - restrict number of rows
- `OFFSET` - skip rows
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

**Day 4 Reflection (February 10, 2026):**
- What went well: Aggregates clicked immediately! Can now answer business questions
- What was challenging: Remembering when to use COUNT(*) vs COUNT(column)
- Energy level: 9/10
- Confidence level: 9/10 (feeling like a real analyst!)
- Favorite moment: Realizing I can now answer "What's our total revenue?"
- Tomorrow's excitement: GROUP BY will unlock even more power!

**Day 3 Reflection (February 9, 2026):**
- What went well: IN operator clicked immediately, HackerRank getting easier
- What was challenging: Complex WHERE logic with multiple conditions
- Energy level: 8/10
- Confidence level: 8/10
- Favorite moment: Solving Weather Observation Station 5 with UNION!
- Tomorrow's excitement: Ready to learn aggregate functions!

**Day 2 Reflection (February 8, 2026):**
- What went well: ORDER BY and LIMIT were intuitive
- What was challenging: Remembering query order (WHERE before ORDER BY)
- Energy level: 8/10
- Confidence level: 8/10

**Day 1 Reflection (February 7, 2026):**
- What went well: Completed 2 lessons! Strong momentum established
- What was challenging: Staying focused for 2 hours
- Energy level: 9/10
- Confidence level: 8/10
- Feeling: Excited and motivated!

---

## 🏆 Achievements Unlocked
- ✅ 4-day streak established! 🔥🔥🔥🔥
- ✅ 15+ HackerRank problems solved
- ✅ Can answer business questions with SQL (COUNT, SUM, AVG, MIN, MAX)
- ✅ Mastered filtering, sorting, and aggregating data
- ✅ Portfolio consistently updated
- ✅ Habit forming - consistency established

---

## 📈 Learning Insights

**Patterns I'm Noticing:**
1. SQL problems are like puzzles - breaking them into steps helps
2. Aggregate functions are game-changers for business questions
3. Reading the question 2-3 times prevents mistakes
4. IN operator saves so much typing vs multiple ORs
5. DISTINCT is crucial for "unique" questions
6. HackerRank discussions are gold when stuck
7. Each day builds on the previous - concepts compound!

**Study Habits Working Well:**
- 1 hour daily is sustainable and effective
- Documenting immediately helps retention
- HackerRank for practice > just reading tutorials
- Taking screenshots of solutions for future reference
- GitHub commits create accountability

**What I've Learned About Data Analysis:**
- It's not just about writing queries - it's about answering questions
- Business context matters as much as technical skills
- Simple functions (COUNT, SUM, AVG) solve most problems
- Data analysts translate business questions into SQL

---

## 🎯 Skills Progression

**Week 1 Progress:**
- Day 1: Can retrieve and filter data ✅
- Day 2: Can sort and limit results ✅
- Day 3: Can handle complex logic ✅
- Day 4: Can answer business questions ✅
- Day 5: Will combine aggregates with categories (GROUP BY)
- Day 6: Will connect multiple tables (JOINs)
- Day 7: Will review and solidify Week 1 concepts

**Current Skill Level:** 
From "SQL Beginner" → "Intermediate SQL User"

Can now:
- Write clean SQL queries
- Filter data with complex conditions
- Sort and limit results
- Answer quantitative business questions
- Count, sum, and average data
- Find min/max values
- Work with unique values

**Ready for:**
- GROUP BY (breaking down by categories)
- JOINs (combining multiple tables)
- Real business analysis scenarios

---

*Last updated: February 10, 2026*
*Consistency streak: 4 days | Target completion: October 2026*
*"Learning SQL one day at a time, building toward a Data Analyst career"*
