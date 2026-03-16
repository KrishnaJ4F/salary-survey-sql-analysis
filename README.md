# 💰 Salary Survey Analysis — SQL & Excel

> An end-to-end SQL analysis of salary survey data to uncover compensation trends
> across job roles, experience levels, industries, and locations.

---

## 📌 Problem Statement

Organizations and job seekers often lack clarity on fair compensation benchmarks.
This project answers key business questions using SQL queries on real survey data —
helping both employers set competitive salaries and candidates negotiate better offers.

---

## 🗂️ Dataset

- **Source:** Salary survey dataset (Excel/CSV)
- **Tool:** MySQL + Microsoft Excel
- **Records:** Real survey responses across multiple roles and industries

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| MySQL | Data querying, aggregation, analysis |
| Microsoft Excel | Data cleaning, pivot tables, summary |
| SQL Techniques | GROUP BY, JOINs, CTEs, subqueries, HAVING, ORDER BY |

---

## 🔍 Business Questions Answered

1. What is the average salary by job title and experience level?
2. Which industries offer the highest median compensation?
3. How does salary vary by location/country?
4. What percentage of respondents earn above a specific threshold?
5. Which roles have the widest salary range (min vs max)?

---

## 📊 Key Findings

- **Finding 1:** Developers earn the highest average salary (~89,323), which is about 41% higher than the dataset’s overall average salary (63,386).
- **Finding 2:** Professionals with 20 years of experience earn an average of 86,119, about 63% higher than entry-level respondents (52,734)
- **Finding 3:** The Finance industry offers the most competitive salaries, with an average salary of 82,505, the highest among all industries in the dataset.

---

## 🧠 SQL Techniques Used

```sql
-- Example 1: Average salary by job title
SELECT job_title, ROUND(AVG(salary), 2) AS avg_salary
FROM salary_survey
GROUP BY job_title
ORDER BY avg_salary DESC;

-- Example 2: Salary distribution by experience level
SELECT experience_level, COUNT(*) AS respondents,
       MIN(salary) AS min_sal, MAX(salary) AS max_sal,
       ROUND(AVG(salary), 2) AS avg_sal
FROM salary_survey
GROUP BY experience_level
ORDER BY avg_sal DESC;

-- Example 3: Top-paying industries using CTE
WITH industry_avg AS (
  SELECT industry, ROUND(AVG(salary), 2) AS avg_salary
  FROM salary_survey
  GROUP BY industry
)
SELECT * FROM industry_avg
ORDER BY avg_salary DESC
LIMIT 5;
```

---

## 📁 Project Files

| File | Description |
|---|---|
| `SQL-MILESTONE.sql` | All SQL queries used in the analysis |
| `DA - milestone.xlsx` | Cleaned dataset and Excel pivot summaries |
| `PROJECT DOCUMENTATION Excel & Mysql.docx` | Full project documentation |
| `krishna DA.pptx` | Presentation slides with insights |

---

## 🚀 How to Run

1. Import the dataset into MySQL Workbench
2. Run queries from `SQL-MILESTONE.sql` in sequence
3. View Excel summaries in `DA - milestone.xlsx`

---

## 👤 Author

**Krishna Kumar** — [LinkedIn](https://www.linkedin.com/in/krishna-kumar-41b84633b/) | [GitHub](https://github.com/KrishnaJ4F)
