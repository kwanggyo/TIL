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

<br>

<br>

# `09.10`

# 관계형 데이터베이스(PK, INDEX)

## 데이터베이스

- 데이터를 모아 둔 곳
- 사람들이 원하는 자료를 쉽게 찾을 수 있다.
- 많은 데이터가 있어도 빠르게 찾을 수 있어야 한다.

## 관계형 데이터베이스

- 데이터를 Key, Value 형태로 식별이 가능하도록 한다. → Column, Row
- 테이블 간에 데이터가 1:1, 1:N, N:N 형태로 관계가 존재한다.
- 각 테이블 간의 Key를 통해 서로를 연결한다.

### Primary Key

- 다른 항목과 중복되어 나타날 수 없는 단일 값(Unique)
- 다중 컬럼을 Primary Key로 설정할 수 있다.
- 관계형(Relation)을 완성할 수 있는 가장 중요한 정보
- PK를 이용하면 정확하고 빠르게 찾을 수 있다.

### PK와 INDEX

1. PK를 생성 → INDEX 생성, PK를 삭제→ INDEX 삭제
2. INDEX : 데이터베이스 테이블의 검색 속도를 향상시키기 위한 자료구조
   - 테이블을 대한 동작의 속도를 높여주는 자료 구조
   - Indexes Table이라고 한다. 즉 Index도 테이블의 한 종류이다. (데이터베이스 객체의 한 종류)
   - PK가 아닌 컬럼이라도 INDEX를 생성할 수 있다.

### 데이터베이스 객체

- 데이터베이스 내에 존재하는 논리적인 저장 구조
- Table, View(가상의 테이블 - 테이블 join의 결과 조회), Indexes, synonym, sequence 등
- DDL(Data Define Language)로 생성, 수정 및 삭제가 가능하다.

### DDL

- SQL(Structured Query Language)의 종류 : 데이터 베이스에서 사용되는 언어
- DML(Data Manipulation Language) : SELECT, INSERT, UPDATE, DELETE
- DDL(Date Define Language) : CREATE, DROP 등 객체 관리
- DCL(Data Control Language) GRANT, REVOKE. 객체에 대한 접근 권한 관리
- TCL(Transaction Control Language) : COMMIT, ROLLBACK 등 DML 조작 결과를 제어

<br>

## INDEX

### INDEX의 동작

Pointer, Hash, B + Tree와 같은 알고리즘으로 쉽게 데이터를 조회할 수 있게 했다.

### INDEX를 왜 쓸까?

Q. 테이블 데이터가 100만건이면 오래걸리지 않나요?

A. Indexex란 DB 자료구조를 통해 빠르게 조회할 수 있다.

Q. 인덱스를 많이 만들면 되나요?

A. 인덱스를 잘못 관리하면 오히려 성능이 저하될 수 있다.

- INDEX를 활용하면 안되는 경우
  - DELETE, UPDATE가 자주 일어나는 경우

### INDEX의 장점

- 테이블을 조회하는 속도와 성능 향상
- 시스템의 부하를 줄일 수 있다
- 원하는 데이터를 빠르게 찾을 수 있다. → 전체 테이블 조회가 아니라 원하는 데이터만 조회 가능

### INDEX의 단점

- DB 저장 공간을 차지한다. (꽤 큰 용량을 잡아먹는다. → 테이블의 row만큼의 정보를 저장해야한다)
- 인덱스를 관리하기 위한 작업이 필요하다.
- 잘못 사용할 경우 성능이 저하될 수 있다. (적재적소에 활용이 필요하다)

### INDEX를 잘 쓰려면?

- Where 조건 작성시 Index를 적용할 수 있는 컬럼 조건을 상단에 작성한다.
- Index로 사용된 컬럼은 컬럼값 그대로 사용한다.
  - 적용 : Where Age > 18
  - 적용 불가 : Where Age * 2 > 36
- Between, like, <, > 등 범위 조건 뒤에 Index들은 적용되지 않으니 가장 마지막에 활용한다.
  - 적용  : Where Id='8' and Age > 16
  - 적용 불가 : Where Age > 16 and Id = '8' → Age > 16까지는 Index가 적용되지만 뒤는 적용되지않는다.

### 쿼리 성능을 향상시키려면?

- Table 생성시 PK, Index 등을 잘 구축한다.
- 같은 결과를 출력하더라도 최적화된 쿼리를 작성해야 한다.
- Table Join 순서도 중요하다. (Driving, Driven 테이블)
  - 앞에서 주도하는 테이블에 따라 결과가 달라진다.
- `키워드` : Database Optimizer, Query Tuning, Query Plan