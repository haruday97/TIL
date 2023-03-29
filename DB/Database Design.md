# Database Design
## Relational Database
구조화된 데이터는 하나의 테이블로 표현할 수 있다. 이러한 테이블을 사용하는 DB를 관계형 데이터베이스라고 한다.
## Schema 
스키마(Schema)는 데이터 구조, 제약 조건, 관계 등을 정의한 구조를 말한다.  
스키마는 이러한 것들을 사전에 정의하여 데이터의 일관성과 정확성을 보장하는 역할을 한다.
### Key
키는 데이터베이스에서 테이블의 레코드를 고유하게 식별하는데 사용되는 필드 또는 필드의 집합이다.  
<ul> 
    <li>
        Primary Key : PK는 NULL값을 가질수없는 고유 식별키이다.
    </li>
    <li>
        Alternate Key : PK를 대체하는 고유 식별키이다.
    </li>
    <li>
        Foreign Key : 타 테이블의 PK를 참조하는 키이다.
    </li>
    <li>
        Candidate Key : PK가 될 수 있는 후보키이다.
    </li>
    <li>
        Composite Key : 둘 이상의 열을 결합한 고유 식별키이다.
    </li>
</ul>

### 관계 종류
<ul> 
    <li>
        1:1 관계 : 한 테이블의 레코드가 다른 테이블 레코드와 이어지는 관계
    </li>
    <li>
        1:N 관계 : 한 테이블의 레코드가 다른 테이블 여러 레코드와 이어지는 관계
    </li>
    <li>
        N:N 관계 : 한 테이블의 여러 레코드가 다른 테이블 여러 레코드와 이어지는 관계
    </li>
    <li>
        자기참조 관계 : 한 테이블의 레코드가 테이블 내의 레코드와 이어지는 관계
    </li>
</ul>

### Index
인덱스는 DB에서 검색속도 향상을 위해 사용되는 데이터 구조이다.  
특정 열을 참조할 때 빠른 검색을 가능케해준다.

## ORMs
ORM(Object-Relational Mapping)은 객체 관계 매핑의 약자로 객체지향 프로그래밍 언어와 RDBMS 사이에서 데이터를 변환하고 연결하는 기술이다.  
Employees 테이블에서 성이 'A'로 시작하는 모든 사원을 불러오는 질의문은 다음과 같다.
<pre>
    <code>
        SELECT * 
        FROM Employees
        WHERE last_name LIKE "A%";
    </code>
</pre>
이처럼 데이터를 불러오려면 SQL 문법을 사용해 데이터를 불러와야 했다.  
그러나 ORM은 (예를 들어 JPA) 작성한 Java 코드를 관계형 DB의 쿼리로 자동으로 변환시켜준다.
<pre>
    <code>
        String jpql = "SELECT e FROM Employees e WHERE e.lastName LIKE 'A%'";
        TypedQuery<Employees> query = entityManager.createQuery(jpql, Employees.class);
        List<Employees> employees = query.getResultList();
    </code>
</pre>
비유로 설명하자면 DB는 도서관, ORM은 책을 빌리러 가는 사람, 개발자는 집에 있는 사람이라고 생각할 수 있다.  
도서관은 대여 규칙이 존재하고 책을 빌리러 가는 사람은 규칙을 따라 책을 대여하고, 집에 있는 사람에게 전달하는 역할을 한다.  
즉 개발자는 따로 SQL 쿼리를 작성할 필요가 없어지며 ORM은 개발자로 하여금 비즈니스 로직작성에 집중케하고 유지보수를 편리하게 해준다.  
그러나 단점으로 성능저하, 직관성 저하 등이 있다. 따라서 개발자는 적절하게 쿼리문을 혼용하는 것이 권장된다.  
대표적인 ORM은 다음과 같다.
<ul>
    <li>JPA : JPA(Java Persistence API)는 관계형 데이터베이스의 사용법을 명세한 인터페이스이다.</li> 
    <li>Hibernate : Hibernate는 JPA의 구현체이다. 가장 널리 쓰이며 특히 해외에서 많이 쓰인다. </li>
    <li>Django : Django는 파이썬의 ORM 프레임워크이다.</li>
    <li>Spring Data JPA : Spring Data JPA는 Spring Framework에서 제공하는 모듈 중 하나이다.</li>
</ul>

## Normalization
정규화(Normalization)는 DB설계에서 중복 데이터를 제거하고 데이터를 더 작은 테이블로 분할하는 과정이다.  
정규화의 목적은 데이터의 일관성 유지와 DB성능향상이다.
