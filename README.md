# 📊 SQL Learning Journey

> Documenting my path from zero to Data Analyst

![Progress](https://img.shields.io/badge/Days%20Completed-5%2F270-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-green)
![Streak](https://img.shields.io/badge/Streak-5%20days-red)

---

## Day 5 - GROUP BY Mastery (February 11, 2026)

### What I Learned:
- GROUP BY - split data into groups and aggregate each group separately
- Combining GROUP BY with COUNT, SUM, AVG, MIN, MAX
- Multiple GROUP BY columns (multi-dimensional analysis)
- Query execution order (WHERE before GROUP BY, ORDER BY after)
- The golden rule: Every SELECT column must be in GROUP BY or in aggregate function
- Real business breakdowns (by region, category, country, etc.)

### Queries I Wrote Today:

```sql
-- Count customers by country
SELECT Country, COUNT(*) as customer_count
FROM Customers
GROUP BY Country
ORDER BY customer_count DESC;

-- Total sales by region
SELECT region, SUM(sales) as total_sales
FROM orders
GROUP BY region
ORDER BY total_sales DESC;

-- Average price by category
SELECT category, AVG(price) as avg_price
FROM products
GROUP BY category;

-- Multiple aggregates per group
SELECT 
    category,
    COUNT(*) as product_count,
    AVG(price) as avg_price,
    MIN(price) as min_price,
    MAX(price) as max_price
FROM products
GROUP BY category;

-- Multiple GROUP BY columns (2 dimensions)
SELECT country, city, COUNT(*) as customer_count
FROM customers
GROUP BY country, city
ORDER BY customer_count DESC;

-- Top 10 products by quantity sold
SELECT product_id, SUM(quantity) as total_sold
FROM order_items
GROUP BY product_id
ORDER BY total_sold DESC
LIMIT 10;

-- HackerRank: Top Earners
SELECT (salary * months) as earnings, COUNT(*)
FROM Employee
GROUP BY earnings
ORDER BY earnings DESC
LIMIT 1;

-- Monthly sales analysis
SELECT 
    DATE_TRUNC('month', order_date) as month,
    SUM(amount) as monthly_sales,
    COUNT(*) as order_count,
    AVG(amount) as avg_order_value
FROM orders
GROUP BY DATE_TRUNC('month', order_date)
ORDER BY month;
```

### Key Takeaways:
1. GROUP BY splits data into groups and runs aggregates on each group separately
2. Without GROUP BY: one total for everything
3. With GROUP BY: one total for EACH category/group
4. Every column in SELECT must be in GROUP BY OR in an aggregate function
5. Query order: SELECT → FROM → WHERE → GROUP BY → ORDER BY → LIMIT
6. WHERE filters rows BEFORE grouping, HAVING filters groups AFTER (next lesson!)
7. Can group by multiple columns for multi-dimensional analysis

### Business Questions I Can Now Answer:
- **"Total revenue by region?"** → `GROUP BY region`
- **"How many customers per country?"** → `GROUP BY country`
- **"Average order value by customer?"** → `GROUP BY customer_id`
- **"Top selling products?"** → `GROUP BY product_id, ORDER BY SUM(quantity) DESC`
- **"Monthly sales trends?"** → `GROUP BY month`
- **"Revenue by product category?"** → `GROUP BY category`
- **"Customers by city and country?"** → `GROUP BY country, city`

### The Game-Changer Moment:
Before: "Total sales: $500,000" (one number, not very useful)
After: 
- North: $150,000 (30%)
- South: $120,000 (24%)  
- East: $130,000 (26%)
- West: $100,000 (20%)
**Now I can identify which regions need attention!**

### HackerRank Progress:
- Problems Solved Today: 5 ✅
- Total Problems Solved: 20+
- Sections: Aggregation (with GROUP BY concepts)
- Success Rate: 100%

### Challenges Faced:
- Remembering the golden rule (every SELECT column in GROUP BY or aggregate)
- Understanding query execution order (WHERE before GROUP BY)
- Top Earners problem took time but finally clicked!
- Realizing GROUP BY creates one row per unique value/combination

### Time Spent: 1 hour
### Exercises Completed: 
- 5 HackerRank problems
- 8 practice GROUP BY queries on W3Schools
- Real business analysis scenarios

### Tomorrow's Goal:
- Learn HAVING clause (filter groups after aggregation)
- More advanced GROUP BY scenarios
- Prepare for Week 1 review

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

### HackerRank Progress:
- Problems Solved: 5 ✅
- Total Problems: 15+
- Section: Aggregation

### Time Spent: 1 hour

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

-- Complex logic with parentheses
SELECT * FROM movies 
WHERE (year > 2000 OR director = 'Pixar') 
AND rating > 8;

-- IN operator (cleaner than multiple ORs)
SELECT * FROM movies 
WHERE director IN ('Pixar', 'Disney', 'DreamWorks');

-- HackerRank: Filter cities starting with vowels
SELECT DISTINCT CITY 
FROM STATION 
WHERE LEFT(CITY, 1) IN ('A','E','I','O','U');
```

### Key Takeaways:
1. AND requires BOTH conditions to be true (narrows results)
2. OR requires AT LEAST ONE condition to be true (widens results)
3. Use parentheses () to control order of operations
4. IN is cleaner than multiple OR statements
5. DISTINCT removes duplicate values

### HackerRank Progress:
- Problems Solved: 5/5 ✅
- Total Problems: 10

### Time Spent: 1 hour

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
```

### Key Takeaways:
1. ORDER BY changes display order, not which rows are selected
2. Default sort is ascending (ASC)
3. LIMIT always comes at the END of the query
4. Can sort by multiple columns

### HackerRank Progress:
- Problems Solved: 5/5 ✅

### Time Spent: 1 hour

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
```

### Key Takeaways:
1. SQL is not case-sensitive but UPPERCASE for keywords is convention
2. Every query needs SELECT and FROM
3. WHERE clause filters ROWS
4. Use semicolon ; to end queries
5. LIKE uses % as wildcard

### Time Spent: 1 hour

---

## 📊 Progress Tracker

### Month 1: SQL Foundations
- ✅ Day 1 - SQL Basics (Feb 7, 2026)
- ✅ Day 2 - Sorting & Filtering (Feb 8, 2026)
- ✅ Day 3 - Advanced Filtering (Feb 9, 2026)
- ✅ Day 4 - Aggregate Functions (Feb 10, 2026)
- ✅ Day 5 - GROUP BY Mastery (Feb 11, 2026)
- ⬜ Day 6 - HAVING Clause & Advanced GROUP BY
- ⬜ Day 7 - Week 1 Review & Practice

### Stats
- **Total Days Completed:** 5/270
- **Actual Days Elapsed:** 5 days
- **Current Streak:** 5 days 🔥🔥🔥🔥🔥
- **Skills Acquired:** SELECT, WHERE, ORDER BY, LIMIT, AND, OR, NOT, IN, DISTINCT, COUNT, SUM, AVG, MIN, MAX, GROUP BY
- **HackerRank Problems Solved:** 20+
- **Total Exercises Completed:** 46+
- **Next Milestone:** Complete Week 1 (Day 7) - almost there!

---

## 🎯 Learning Goals

**Short-term (Week 1):**
- ✅ Master SQL fundamentals (filtering ✓, sorting ✓, aggregates ✓, GROUP BY ✓)
- ⬜ Learn HAVING (Day 6)
- ⬜ Week 1 review and consolidation (Day 7)

**Short-term (Month 1):**
- ⬜ Learn JOINs (Week 2)
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
- W3Schools SQL TryIt - Quick practice with pre-loaded data
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

### Day 5:
- `GROUP BY` - split data into groups, aggregate separately
- Multiple GROUP BY columns
- Combining GROUP BY with all aggregate functions
- Query execution order (WHERE → GROUP BY → ORDER BY)
- Golden rule: SELECT columns must be in GROUP BY or aggregate
- Multi-dimensional analysis (country + city)
- Business breakdowns (by category, region, time period)

### Day 4:
- `COUNT()`, `COUNT(DISTINCT)`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
- `FLOOR()`, `CEIL()`, `ROUND()`
- Combining aggregates with arithmetic

### Day 3:
- `AND`, `OR`, `NOT`, `IN`, `NOT IN`
- `DISTINCT`, `COUNT(DISTINCT column)`
- `LEFT()`, `LENGTH()`, `SUBSTRING()`
- `%` (modulo), `UNION`
- Parentheses for complex logic

### Day 2:
- `ORDER BY`, `ASC`, `DESC`
- `LIMIT`, `OFFSET`
- Multiple column sorting

### Day 1:
- `SELECT`, `FROM`, `WHERE`
- `=, !=, <, >, <=, >=`
- `BETWEEN`, `AND, OR`
- `LIKE`, `%` (wildcard)

---

## 💪 Daily Reflections

**Day 5 Reflection (February 11, 2026):**
- What went well: GROUP BY clicked immediately! This is a GAME-CHANGER
- What was challenging: Remembering the golden rule at first
- Energy level: 10/10
- Confidence level: 9/10 (feeling like a real data analyst now!)
- Favorite moment: When I realized GROUP BY unlocks multi-dimensional analysis
- AHA moment: "Revenue by region" instead of just "total revenue" - this is what managers need!
- Tomorrow's excitement: HAVING clause to filter groups!

**Day 4 Reflection (February 10, 2026):**
- What went well: Aggregates clicked immediately!
- What was challenging: COUNT(*) vs COUNT(column)
- Energy level: 9/10
- Confidence level: 9/10
- Favorite moment: Answering "What's our total revenue?"

**Day 3 Reflection (February 9, 2026):**
- What went well: IN operator clicked immediately
- What was challenging: Complex WHERE logic
- Energy level: 8/10
- Confidence level: 8/10
- Favorite moment: Solving Weather Observation Station 5 with UNION!

**Day 2 Reflection (February 8, 2026):**
- What went well: ORDER BY and LIMIT were intuitive
- Energy level: 8/10
- Confidence level: 8/10

**Day 1 Reflection (February 7, 2026):**
- What went well: Strong momentum established
- Energy level: 9/10
- Confidence level: 8/10

---

## 🏆 Achievements Unlocked
- ✅ 5-day streak! 🔥🔥🔥🔥🔥 (habit established!)
- ✅ 20+ HackerRank problems solved
- ✅ **Can perform multi-dimensional business analysis with GROUP BY**
- ✅ Can answer complex business questions (by region, category, time)
- ✅ Mastered core SQL: filtering, sorting, aggregating, grouping
- ✅ Portfolio consistently updated (5 days straight!)
- ✅ Almost completed Week 1! (2 more days)

---

## 📈 Learning Insights

**Major Breakthroughs:**
1. **GROUP BY is the difference between basic SQL and data analysis**
   - Before: One total number
   - After: Breakdown by categories with actionable insights
2. **Every business question has a GROUP BY pattern:**
   - "by X" = GROUP BY X
   - "for each Y" = GROUP BY Y
   - "per Z" = GROUP BY Z
3. **Multi-dimensional analysis unlocks deeper insights:**
   - GROUP BY country, city
   - GROUP BY category, subcategory
   - GROUP BY year, month

**Patterns I'm Noticing:**
- SQL builds on itself perfectly (each day uses previous days' concepts)
- GROUP BY + aggregates = most powerful SQL combination
- Real business questions always need GROUP BY
- Reading the question carefully reveals which column to GROUP BY
- Practice makes the syntax automatic

**Study Habits Working Well:**
- 1 hour daily = sustainable and highly effective
- Immediate documentation = better retention
- HackerRank + W3Schools practice = perfect combo
- Each concept clicks after 3-5 practice queries
- Writing queries from scratch > copy-pasting

**What Data Analysts Actually Do:**
- Not just writing queries - answering business questions
- Breaking down totals to find patterns
- Identifying what's working vs what needs attention
- GROUP BY is used in 80% of business analysis queries

**Confidence Growth:**
- Day 1: "I hope I can learn SQL"
- Day 5: "I can analyze business data!"

---

## 🎯 Skills Progression

**Week 1 Progress:**
- Day 1: Can retrieve and filter data ✅
- Day 2: Can sort and limit results ✅
- Day 3: Can handle complex logic ✅
- Day 4: Can answer simple business questions ✅
- Day 5: **Can perform multi-dimensional analysis** ✅ ← HUGE!
- Day 6: Will learn to filter groups (HAVING)
- Day 7: Will consolidate Week 1 knowledge

**Current Skill Level:** 
**Intermediate SQL Analyst** (was beginner 5 days ago!)

**Can now answer:**
- ✅ "How many customers do we have?" → COUNT(*)
- ✅ "What's our total revenue?" → SUM(revenue)
- ✅ "What's the average order value?" → AVG(order_amount)
- ✅ "What's revenue by region?" → GROUP BY region, SUM(revenue)
- ✅ "Which products sell best?" → GROUP BY product, SUM(quantity)
- ✅ "How many customers per country?" → GROUP BY country, COUNT(*)
- ✅ "Monthly sales trends?" → GROUP BY month, SUM(sales)
- ✅ "Top 10 customers by spend?" → GROUP BY customer, SUM(spend), ORDER BY, LIMIT

**Ready for:**
- HAVING clause (filter groups)
- JOINs (combine multiple tables)
- Window functions (advanced analytics)
- Real-world projects

---

## 🚀 Real-World Applications

**SQL Skills Mastered = Job-Ready Skills:**

**What I can do now that employers want:**
1. ✅ Extract data from databases (SELECT, WHERE)
2. ✅ Sort and prioritize results (ORDER BY, LIMIT)
3. ✅ Calculate business metrics (aggregates)
4. ✅ **Break down performance by categories (GROUP BY)**
5. ✅ Identify trends and patterns
6. ✅ Answer stakeholder questions with data

**Actual job tasks I can handle:**
- "Show me sales by region" ← Can do!
- "Which product categories perform best?" ← Can do!
- "How many customers per country?" ← Can do!
- "What's our average transaction value by month?" ← Can do!
- "Top 10 products by revenue?" ← Can do!

**This is what junior data analysts do daily!** 💼

---

*Last updated: February 11, 2026*
*Consistency streak: 5 days 🔥 | Target completion: October 2026*
*"From SQL beginner to data analyst - one GROUP BY at a time"*
