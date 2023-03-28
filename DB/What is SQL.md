# What is SQL
DB는 데이터를 저장하는 서버이며 테이블과 열, 행으로 구성된 데이터의 집합이다.  
SQL은 DB를 다루기 위한 언어이며 이를 이용해 DB에 데이터를 추가, 검색, 수정, 삭제 (CRUD)를 할 수 있다.
## SQL vs NoSQL
DB는 크게 SQL을 기반으로한 관계형DB와 NoSQL로 데이터를 다루는 비관계형DB로 구분된다.  
대표적인 관계형 DB는 MySQL, Oracle, SQLite 등이 있다.  
대표적인 비관계형 DB는 Mongo DB 등이 있다.
## Transaction
트랜잭션(Transaction)이란 여러 개의 작업을 하나로 묶은 실행 유닛이다.
### ACID
ACID는 하나의 트랜잭션의 안정성을 보장하기 위해 필요한 성질이다.
<ul>
    <li>
        원자성(Atomicity) : 트랜잭션의 모든 작업이 하나의 논리단위로 처리되어야한다.
   </li>
    <li>
        일관성(Consistency) : 트랜잭션의 실행전과 후의 DB상태가 항상 일관적이어야한다.
   </li>
    <li>
        고립성(Isolation) : 트랜잭션은 다른 트랜잭션의 작업에 대해 영향받지 말아야한다.
   </li>
    <li>
        지속성(Durability) : 트랜잭션이 완료되면 그 결과는 항상 유지되어야 한다.
   </li>
</ul>
