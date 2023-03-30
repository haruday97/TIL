# Queries
## SQL 종류
SQL은 다양한 문법이 있다. 인간의 언어에서 주어, 동사, 명사, 형용사 등을 구분하는 것과 같이 SQL은 문법을 다음과 같이 분류한다.  
<ul>
    <li>
        Data Definition Language : DDL은 데이터를 정의할 때 사용하는 언어이다. (CREATE, DROP, ...)
    </li>
    <li>
        Data Manipulation Language : DML은 데이터를 저장할 때 사용하는 언어이다. (INSERT, DELETE, UPDATE, ...)
    </li>
    <li>
        Data Control Language : DCL은 데이터베이스에 대한 접근 권한과 관련된 언어이다. (GRANT, REVOKE, ...)
    </li>
    <li>
        Data Query Language : DQL은 정해진 스키마 내에서 쿼리할 수 있는 언어이다. (SELECT)
    </li>
    <li>
        Transaction Control Language : TCL은 DML을 거친 데이터의 변경사항을 수정하는 언어이다. (COMMIT, ROLLBACK, ...)
    </li>
</ul>

## Query
쿼리(Query)란 데이터베이스에서 데이터를 조회하거나 조작하기 위해 사용하는 명령어를 말한다.  
DB 내에 저장된 데이터를 검색하고 필터링하거나 특정 조건에 따라 업데이트하거나 삭제하는 등의 작업을 수행할 때 쿼리를 사용한다.
### 데이터베이스
#### 데이터베이스 생성
<pre>
    <code>
        CREATE DATABASE NAME_DB;
    </code>
</pre>
#### 데이터베이스 사용
<pre>
    <code>
        USE NAME_DB;
    </code>
</pre>
### 테이블
#### 테이블 생성
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
#### 테이블 확인
<pre>
    <code>
        DESCRIBE NAME_TABLE
    </code>
</pre>
### SELECT
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
    </code>
</pre>
### WHERE
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL = condition
    </code>
</pre>

#### NOT
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE NOT COL = condition
    </code>
</pre>
#### LIKE
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL LIKE 'A%'
    </code>
</pre>
#### IN
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL IN ("A","B")
    </code>
</pre>
#### IS NULL
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL IS NULL
    </code>
</pre>
#### BETWEEN
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        WHERE COL BETWEEN A AND B
    </code>
</pre>
### ORDER BY
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        ORDER BY COL
    </code>
</pre>
### GROUP BY
<pre>
    <code>
        SELECT * 
        FROM NAME_TB
        GROUP BY COL
    </code>
</pre>
### JOIN
#### INNER JOIN
<pre>
    <code>
        SELECT * 
        FROM TB1
        INNER JOIN TB2 ON TB1.COL = TB2.COL
    </code>
</pre>
#### OUTER JOIN
<pre>
    <code>
        SELECT * 
        FROM TB1
        LEFT OUTER JOIN TB2 ON TB1.COL = TB2.COL
    </code>
</pre>


