# 🔍 LeetCode 178 – Rank Scores (SQL)

## 📌 Problem
Given a table of scores, assign ranks with the following rules:
- Higher score gets a better rank  
- Same scores share the same rank  
- Ranking should be continuous (no gaps)  

## 💡 Approach
Used the `DENSE_RANK()` window function to assign ranks without skipping values in case of ties.

## 🧾 Solution
```sql
SELECT 
    score,
    DENSE_RANK() OVER (ORDER BY score DESC) AS rank
FROM Scores;
