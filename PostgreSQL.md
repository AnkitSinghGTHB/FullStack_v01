# PostgreSQL Queries (Basic to Advanced)

## 🟢 Basic Queries

### SELECT
- SELECT * FROM table;
- SELECT column1, column2 FROM table;
- SELECT DISTINCT column FROM table;

### WHERE Clause
- SELECT * FROM table WHERE column = 'value';
- SELECT * FROM table WHERE column > 100;
- SELECT * FROM table WHERE column IS NULL;

### ORDER BY
- SELECT * FROM table ORDER BY column ASC;
- SELECT * FROM table ORDER BY column DESC;

### LIMIT / OFFSET
- SELECT * FROM table LIMIT 10;
- SELECT * FROM table LIMIT 10 OFFSET 5;

### INSERT
- INSERT INTO table (col1, col2) VALUES ('val1', 'val2');

### UPDATE
- UPDATE table SET col1 = 'val' WHERE col2 = 5;

### DELETE
- DELETE FROM table WHERE condition;

## 🟡 Intermediate Queries

### JOINs
- SELECT * FROM a INNER JOIN b ON a.id = b.a_id;
- SELECT * FROM a LEFT JOIN b ON a.id = b.a_id;
- SELECT * FROM a RIGHT JOIN b ON a.id = b.a_id;
- SELECT * FROM a FULL OUTER JOIN b ON a.id = b.a_id;

### GROUP BY + HAVING
- SELECT col, COUNT(*) FROM table GROUP BY col;
- SELECT col, COUNT(*) FROM table GROUP BY col HAVING COUNT(*) > 1;

### CASE Statement
- SELECT col, CASE WHEN col > 10 THEN 'High' ELSE 'Low' END FROM table;

### Aliases
- SELECT col AS alias_name FROM table;

### IN / NOT IN
- SELECT * FROM table WHERE col IN (1, 2, 3);

### BETWEEN
- SELECT * FROM table WHERE col BETWEEN 10 AND 20;

## 🔵 Advanced Queries

### Subqueries
- SELECT * FROM table WHERE id IN (SELECT id FROM another_table);
- SELECT col, (SELECT MAX(score) FROM scores WHERE user_id = users.id) AS max_score FROM users;

### CTE (WITH clause)
- WITH recent_orders AS (
    SELECT * FROM orders WHERE order_date > NOW() - INTERVAL '30 days'
  )
  SELECT * FROM recent_orders;

### Window Functions
- SELECT id, score, RANK() OVER (ORDER BY score DESC) FROM scores;
- SELECT id, dep, SUM(salary) OVER (PARTITION BY dep) FROM employees;

### JSON / JSONB
- SELECT data->>'name' FROM json_table;
- SELECT * FROM json_table WHERE data @> '{"key": "value"}';

### UPSERT (INSERT ON CONFLICT)
- INSERT INTO table (id, val) VALUES (1, 'x') 
  ON CONFLICT (id) DO UPDATE SET val = EXCLUDED.val;

### ARRAY Functions
- SELECT * FROM table WHERE 3 = ANY(array_col);
- SELECT unnest(array_col) FROM table;

### Full-text Search
- SELECT * FROM articles WHERE to_tsvector(content) @@ to_tsquery('postgres');

### Materialized Views
- CREATE MATERIALIZED VIEW view_name AS SELECT * FROM table;
- REFRESH MATERIALIZED VIEW view_name;

### Custom Functions
- CREATE FUNCTION add(a integer, b integer) RETURNS integer AS $$
  BEGIN
    RETURN a + b;
  END;
  $$ LANGUAGE plpgsql;
