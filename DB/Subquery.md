# Subquery

## 개요
서브쿼리란 하나의 SQL문장 안에서 다른 SQL문장을 사용하는 것을 말한다.  
서브쿼리는 SELECT, FROM, WHERE, HAVING 절 등에서 사용할 수 있다.

## 유의점
<ul>
    <li>
        서브쿼리는 소괄호로 감싸야한다.
    </li>
    <li>
        서브쿼리에서는 ORDER BY를 사용하지 못한다.
    </li>
    <li>
        서브쿼리의 결과를 하나의 칼럼으로 사용할 수 있다.
    </li>
</ul>

## 사용법
사용법은 다음과 같다.

### SELECT
<pre><code>SELECT name, age
FROM my_table
WHERE age > (SELECT AVG(age) FROM my_table);</code></pre>

### INSERT
<pre><code>INSERT INTO new_table (col1, col2, col3)
SELECT col1, col2, col3 FROM old_table
WHERE col4 = (SELECT MAX(col4) FROM old_table);</code></pre>

### UPDATE
<pre><code>UPDATE my_table
SET my_column = (SELECT other_column FROM other_table WHERE other_table.id = my_table.id)
WHERE my_column IS NULL;</code></pre>

### DELETE
<pre><code>DELETE FROM my_table
WHERE id IN (SELECT id FROM other_table WHERE condition);</code></pre>

### WHERE
<pre><code>SELECT col1, col2
FROM my_table
WHERE col3 = (SELECT MAX(col3) FROM my_table);</code></pre>

### HAVING
<pre><code>SELECT col1, AVG(col2)
FROM my_table
GROUP BY col1
HAVING AVG(col2) > (SELECT AVG(col2) FROM my_table);</code></pre>

### FROM
<pre><code>SELECT col1, col2, col3
FROM (SELECT id, col1, col2, col3 FROM my_table WHERE col4 = 'value') AS sub_table;</code></pre>

