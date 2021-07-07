# `07.07`

# DevOps

개발(Development)과 운영(Operations)을 합쳐 놓은 말

개발 테스트 / 배포, 운영 유지보수

REAL - Time Communication 중요 !

### 잘 수행하기 위한 조건

1. 반복적인 작업들을 Tool을 이용해서 자동화

2. 팀원 모두가 알고 있는 하나의 공유된 지표가 필요

3. 장애나 이슈가 있을 때 혼자만 알지 말고 팀원들과 공유 필요

<br>

# JIRA

JIRA : 이슈트래킹 시스템, 이슈 추적 툴

이슈 : 내가 해야할 일들을 쪼개서 하나의 이슈라고도 함

### 이슈 타입

Story : 유저가 어떤 일을 해야 하는지 스토리 라인으로 만듦 ex) - 사용자가 로그인을 한다, 회원가입을 한다.

Task : 하나의 할 일 - ex) 로그인을 하기 위해 로직 개발, 창 개발

Bug : 소프트웨어 개발한 뒤에 Bug 발생 시

Epic : 하나의 큰 틀(테마)

### 용어

Assignee : 담당자

Reporter : 생성자

Status : 이슈가 현재 어떤 단계에 있는 지를 나타냄 (workflow : 어떤 단계로 흘러갈지 커스텀 가능)

Component : 하나의 개발 항목, 위의 타입으로 묶기 애매할 때 사용 - ex) Frontend

Resolution : 어떻게 끝이 났는지 표시(이 부분이 표시되어야 완료가 되었는지 판단)

<br>

## JQL(Jira Query Language)

Jira Issue를 구조적으로 검색하기 위해 제공하는 언어

SQL(Standard Query Language)과 비슷한 문법

Jira의 각 필드들에 맞는 특수한 예약어들을 제공

쌓인 Issue들을 재가공해 유의미한 데이터를 도출해 내는데 활용(Gadget, Agile Board 등)

Issue - Search for Issue - Current User(현재 로그인한 유저-나) - 조건을 걸고 Advanced를 클릭하면 SQL과 비슷한 언어로 바뀜

처음에 어려우면 조건을 걸고 Advanced로 누르면 바뀜 → 한계가 있을 수 있음

- JQL Operators

- 날짜 관련 기능(Relative Dates)

- JQL Keywords

- JQL Functions

<br>

## Filter Share

내가 생성한 필터를 남들도 같이 검색할 수 있게 Save Flilter → 이름을 정해서 저장

Find Filter → Popular로 가면 남들이 공유해 놓은  Filter를 볼 수 있다, 즐겨찾기 가능

<br>

## DashBoard & Gadget

내가 원하는 대로 DashBoard를 Gadget으로 꾸민다.

내가 홈화면에 들어왔을 때 보고 싶은 지표를 먼저 볼 수 있다.

### DashBoard

DashBoard → Manage DashBoard → Create New DashBoard

공유 가능

별을 누르면 맨 처음에 DashBoard에 접속했을 때 볼 수 있음

### Add a gadget

Assignment to Me : 나에게 할당된 미완성 이슈들을 보여줌(지라 기본)

Filter Results : Filter를 지정하여 해당 이슈를 보여줌, ex) 나의 미완료 학습

Pie Chart : 필터들을 항목별로 구분해서 보여줌, ex) 이번주이슈 Filter + Component 하면 어떤 식으로 설정되어 있는지 보여줌

Heat Map : Pie Chart와 같은데 비율만큼 글자의 크기가 커짐

<br>

## Agile Board

Scrum과 Kanban 모드가 있음

### Scrum

스프린트라는 주기에 Backlog를 담고 어떻게 진행 중인지 표현

스프린트가 끝나면 다음 스프린트에 다시 담고 진행

### Kanban

프로젝트 이슈 / 필터를 걸어서 생성 가능

단계별로 어떻게 진행되고 있는지 표현

<br>

## 현업에서 JIRA 활용

### 스마트 커밋

Gitlab과 같은 저장소 관리 툴과 연결해준다.

Commit을 할 때 이슈의 키를 달아서 하면 링크가 달리게 됨

자동으로 커밋을 올리면서 이슈를 진행 가능

\#close를 하게 되면 커밋하면서 이슈를 끝낼 수 있음

### 플러그인