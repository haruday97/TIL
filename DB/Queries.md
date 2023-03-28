# Queries
## 데이터베이스
### 데이터베이스 생성
<pre>
    <code>
        CREATE DATABASE NAME_DB;
    </code>
</pre>
### 데이터베이스 사용
<pre>
    <code>
        USE NAME_DB;
    </code>
</pre>
## 테이블
### 테이블 생성
<pre>
    <code>
        CREATE TABLE NAME_TABLE (
            필드명 데이터타입
        )
    </code>
</pre>
ex)
<pre>
    <code>
        CREATE TABLE user (
            id int PRIMARY KEY AUTO_INCREMENT,
            name varchar(255),
            email varchar(255)
        )
    </code>
</pre>
### 테이블 확인
<pre>
    <code>
        DESCRIBE NAME_TABLE
    </code>
</pre>
## SELECT
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
    </code>
</pre>
## WHERE
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL = condition
    </code>
</pre>

### NOT
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE NOT COL = condition
    </code>
</pre>
### LIKE
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL LIKE 'A%'
    </code>
</pre>
### IN
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL IN ("A","B")
    </code>
</pre>
### IS NULL
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL IS NULL
    </code>
</pre>
### BETWEEN
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL BETWEEN A AND B
    </code>
</pre>
## ORDER BY
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        ORDER BY COL
    </code>
</pre>
## GROUP BY
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        GROUP BY COL
    </code>
</pre>
## JOIN
## INNER JOIN
<pre>
    <code>
        SELECT * 
        FROM TB1
        INNER JOIN TB2 ON TB1.COL = TB2.COL
    </code>
</pre>
## OUTER JOIN
<pre>
    <code>
        SELECT * 
        FROM TB1
        LEFT OUTER JOIN TB2 ON TB1.COL = TB2.COL
    </code>
</pre>


