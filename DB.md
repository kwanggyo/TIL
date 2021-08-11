# `07.19`

# DB

## DB 설계 추가 내용(면접, CS 지식)

1. **auto increment**

   보통 pk를 auto increment로 많이 함 → 타입을 보통 int로 잡는데(1부터 시작 → -가 될 일이 없는데 범위가 -까지 있음)

   ⇒ 바이트를 줄이면서 양을 늘리는 방법 → unsigned(1부터 시작)

   JPA에도 unsigned로 받는 타입이 있음

2. **NOT NULL**

   최대한 NOT NULL로 잡지 않기 → NOT NULL로 잡으면 boolean타입이 true, false, null이 됨 → true, false만 되도록 시작과 동시에 초기화

3. **VARCHAR vs CHAR(고정 문자열)**

   어떤게 더 빠른지 → CHAR

   VARCHAR 내가 사용하는 문자열의 수만큼 채워넣고 나머지를 블링크로 처리

   CHAR는 CHAR(10)이면 이 값만 선언하고 시작하기 때문에

   고정된 값을 사용할 거면 CHAR가 좋음

   ex) 핸드폰 번호, 주민등록번호, 우편번호 등

<br>

<br>

# `08.11`

## DATABASE

의미 있게 구조화하여 저장된 정보

### Relational Database

Atomicity, Consistency, Isolation, Durability

Normalization - 1NF, 2NF, 3NF

Scalability(Scale-up, not scale out)

ANSI SQL문법, JOIN 기능

모델링 경직, 비 효율적인 공간활용, 빅데이터에 비효율적

- PostgreSQL, MySQL, SQL Server, ORACLE

### NewSQL

RDB와 NoSQL의 장점을 합침

Partitioning/ShardingConcurrency Control

Replication

Crash Recovery

- nuoDB, CockroachDB