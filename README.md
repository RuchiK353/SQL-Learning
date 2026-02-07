📊 SQL Learning Journey

Documenting my path from zero to Data Analyst

Day 1 - SQL Basics (February 7, 2026)
What I Learned:

SELECT statement - retrieves data from database
FROM clause - specifies which table
WHERE clause - filters data based on conditions
Comparison operators: =, !=, <, >, <=, >=
Logical operators: AND, OR
Special operators: BETWEEN, IN, LIKE

Queries I Wrote Today:
sql-- Get all columns from a table
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
Key Takeaways:

SQL is not case-sensitive but UPPERCASE for keywords is convention
Every query needs SELECT and FROM
WHERE clause filters ROWS
Use semicolon ; to end queries
LIKE uses % as wildcard (any characters)

Time Spent: 1 hour
Exercises Completed: SQLBolt Lessons 1-3 (14 exercises)
Tomorrow's Goal:

Learn ORDER BY and LIMIT
Solve 5 HackerRank problems
Practice sorting data


📊 Progress Tracker
Month 1: SQL Foundations

✅ Day 1 - SQL Basics (Feb 7, 2026)
⬜ Day 2 - Sorting & Filtering
⬜ Day 3 - Advanced Filtering
⬜ Day 4 - Aggregate Functions
⬜ Day 5 - GROUP BY Practice
⬜ Day 6 - Practice Day
⬜ Day 7 - Week Review

Stats

Total Days Completed: 1/270
Current Streak: 1 day 🔥
Skills Acquired: SELECT, WHERE, filtering, pattern matching
Next Milestone: Complete Week 1 (Day 7)


🎯 Learning Goals
Short-term (Month 1):

✅ Master SQL fundamentals
⬜ Complete 3 SQL projects
⬜ Earn HackerRank SQL certification

Long-term (9 months):

⬜ Build complete data analyst portfolio
⬜ Master SQL, Excel, Power BI, Python
⬜ Land first Data Analyst job


🛠️ Tools & Resources
Currently Using:

SQLBolt - Interactive SQL exercises
SQLiteOnline - Practice environment
Mode Analytics - SQL tutorials
Alex The Analyst (YouTube) - Video lessons

Tech Stack:

SQL (PostgreSQL/SQLite)
GitHub (Portfolio & Documentation)

Coming Soon:

Excel (Month 3)
Power BI (Month 3-4)
Python (Month 5-6)


📚 Concepts Mastered
Day 1:

SELECT - retrieve data
FROM - specify table
WHERE - filter rows
=, !=, <, >, <=, >= - comparison operators
BETWEEN - range filtering
AND, OR - logical operators
LIKE - pattern matching
% - wildcard character


💪 Daily Reflections
Day 1 Reflection:

What went well: Completed all exercises, understood SELECT and WHERE
What was challenging: Understanding LIKE and wildcards at first
Energy level: 8/10
Confidence level: 7/10
Looking forward to: Learning sorting tomorrow!


Last updated: February 7, 2026
Repository created as part of 270-day Data Analyst journey
