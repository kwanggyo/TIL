



### 01.13

#### 프로그램의 3가지 형식

##### 1. 저장

- 변수
- 문자, boolean
- list, dictionary

##### 2. 반복

- for(범위가 필요)
- whil(조건이 필요)

##### 3. 조건

- If / elif / else



### 01.14

#### 함수

##### 1. 내장함수

- print, len, abs 등 -> build-in 이라고도 함

##### 2. 외장함수

- random 등

- import를 통해서 모듈을 불러온다.
- random.choice : random 중에서 choice를 가져다가 쓴다. 여기서 choice는 임의적으로 하나의 요소를 선택해준다.

##### 3. 활용하기 위한 operator, type



:memo: 크롤링

: 웹페이지에 들어가서 원하는 정보를 가져오는 것

-> 파이썬이 하도록 코드를 짜야한다.

- 주소창에 주소를 치면 서버로 요청을 보낸다.
- 서버(server)에서 정보를 준다는 말은 html, css, js 등을 주는 것이다. 브라우저(크롬)는 이것들을 꾸며서 화면에 보여준다.
- 웹에서의 server는 컴퓨터를 뜻한다.



:memo: API

: 다른 두 개체가 소통할 수 있게 만드는 중간개체

ex) 사람 - (말, 제스쳐) - 사람

​	 사람 - (모니터, 마우스, 키보드) - 컴퓨터

​	 사람 - (터치, 음성) - 스마트폰 

-> 핵심은 소통

- 프로그램 - (API) - 프로그램 : 프로그램이 소통하기 위한 규칙

- 보통 정보를 주고 받는다고 표현한다.

ex) 우체국에서 편지를 보낼 때, 지켜줘야 하는 것 : 우측상단 우표, 좌측상단 보내는 사람, 우측하단 받는 사람 등

- 위와 같이 프로그램끼리 소통할 때에도 규칙이 있는데, 이것이 API 문서에 정리되어 있음



:memo: JSON

: 우리는 원하는 정보만 받아오면 된다. 그러한 정보 타입이 JSON이고 가공하기 쉽기 때문에 사용한다.

- 데이터 타입은 사용자를 위함과 프로그램을 위함이 있는데 원하는 형식을 가져오는 것이 편리하다.



:cherries: Git

: 형상관리(버전관리)를 통해 코드에서 버전 관리를 할 수 있게 도와준다.

1. git init

   : 대상이 되는 폴더를 git으로 관리하기 시작

2.  git status

   : 어떤 변경사항이 있는지 알아보기 위한 명령어

3.  Untracked files

   : 아직 변경사항이 관리되고 있지 않은 파일들(한번도 commit을 안한 파일들)

4.  stage 단계로 올리기

   : 변경사항이 관리되기 시작하는 단계

   - gid add 파일명 - 기록할 대상을 모으는 단계
   - git config --global user.name kwanggyo
   - git config --global user.email dlrhkdry29@gmail.com

5.  commit 단계 - 실제 기록이 일어나는 단계

   : commit을 해야 버전(기록)이 남음

   - 위의 name, email을 통해 누가 기록하는지 설정을 해놓아야한다.
   - git commit -m '커밋메세지' : 어떤 변경사항이 일어났는지 자세하게 적는 것이 좋다.

6.  git status에 나오지 않으면 모든 변경사항을 기록한 것이다.

7.  git log --oneline(옵션)

   : 기록을 확인한다.
   
8. git remote add origin https://github.com/kwanggyo/TIL.git

   : 원격 저장소를 지정하는데 지정한 이름을 origin이라고 하겠다. + 주소

9. git push origin master

   : 관련 업체(Github, Gitlab 등)로 올리는 단계, 원격(remote) 저장소

**// 정리**

1. 맨처음 폴더를 대상으로 git이 관리할 것인지 설정
2. git init - 폴더당 한번만
   - 만약에 master가 보이면 하지않기(이미 init 됨)
3. 파일을 기록하고 싶다면
   - git add 파일명
   - git commit -m '커밋메세지'
4. 수정사항이 발생했다면
   - 2, 3번 반복(loop)
5. 지금까지 한 것은 내 컴퓨터에만 저장된 것으로 이것을 cloude에 올려야한다.(github, gitlab)

   - git push origin master
6.  추가적인 것은 git.md 참고



### 01.15

:point_right: 폴더, 파일 만들때, 한글x, 띄어쓰기x 대신 _ 사용, 특수문자는 _ 만 사용



:cherries: 무료로 볼 수 있는 웹 강의

1. 생활코딩(비영리) : WEB
2. 노마드 코더
3. 인프런 : 개발관련 강의가 많음(한글)
4. cs50 : 영어



#### 실습(간단하게 정리)

##### 챗봇(텔레그램 이용)

- numOfRow=? : 한번에 나오는 열의 수
- pageNo=? : 데이터의 페이지 수
- 서버는 24시간 동안 항상 켜져있다고 생각(한번 예약을 하고 계속 유지하려면)
  - 이러한 서비스를 다른 컴퓨터를 통해 하는 것 aws, ms azure, pythonanywhere 등
  - ex) tistory.com/10 : 10에 해당하는 서버, tistory.com/1 : 1에 해당하는 서버
  - 위의 페이지를 각각 만들지 않고 variable routing(동적 라우팅)을 이용

##### 파파고

- Client_id, Client_secret 필요(개발자 센터에서 발급)
- pprint : 보기 좋게 만들어줌 ex) pprint.pprint
- request.get(url, headers = headers) : naver에서 요청을 보낼 때는 headers가 필요
- 원하는 데이터에 따라 형식이 다름 ex) query



:memo: 모듈 설치

- 서버를 이용하기 전에 설치(pip install 모듈이름)

  ```shell
  pip install flask
  ```

- 모듈, 함수를 import 해서 사용

- print, len 등 : 내장함수(built-in)

- random, pprint 등 : 외장함수 - 따로 설치하진 않았지만 파이썬을 설치했을 때 같이 들어있던 패키지

- requests, flask(framework) 등 : 3rd party 모듈(라이브러리)

  - 모듈, 라이브러리 : 사용하기 좋게 만들어 놓은 코드 뭉치



### 01.18

:memo: jupyter notebook

: REPL(Read Eval Print Loop) - 파이썬 대화형 개발 환경 중 하나

설정방법

- 파일에 git bash here 클릭
- pip install notebook
- jupyter notebook

단축키

- a(above) : 위에 셀을 추가

- b(below) : 아래에 셀을 추가

- ctrl + enter : 실행

- H : 단축키 도움말

기타 사항

- markdown 문법을 사용하여 풍부한 문서화 가능
- 셀 단위의 코드 실행으로 바로 결과를 알 수 있다.
- 왼쪽이 파란색 : 명령모드, 초록색 : 수정모드



:point_right: 개발할 때 폰트가 중요하다.

: I, l 대문자인지 소문자 인지 모른다.



:memo: D2Coding

: 글자의 폰트(구별하기 쉽게)

설정 - 모양 - 글꼴 맞춤설정 - 고정폭글꼴 - D2Coding



:point_right: PEP-8(python style guide)를 잘 지켜야 한다.



#### 수업정리

##### 1. 기초 문법(Syntax)

1. 주석(Comment)

   - 한 줄 주석 : #

   - 여러줄 주석(multiline string) : # or """ 또는 '''

2. 코드 라인

   - 1줄에 1문장이 원칙

   - 문장은 파이썬이 실행 가능한 최소한의 코드 단위

##### 2. 변수(Variable)

1. 할당 연산자(Assignment Operator)

   - 변수는 = 을 통해 할당

   - type() : 데이터 타입 확인

   - id() : 값의 메모리 주소를 확인

   - 같은 값, 다른 값을 동시 할당 가능

   - 변수와 값의 개수는 같아야 한다.

   - 변수 값을 바꾸는 경우 : 임의의 변경

   - ```python
     x = 1
     y = 2
     change = x
     x = y
     y = change
     print(x, y)
     ```

2. 식별자(Identifiers)

   - 변수, 함수, 모듈 등을 식별하는데 사용되는 이름

   - 영문알파벳(대, 소문자), 밑줄(_), 숫자로 구성

   - 첫글자에 숫자 불가, 대소문자 구별, 길이제한 없음

   - | 사용불가                                                     |
     | ------------------------------------------------------------ |
     | False, None, True, and, as, assert, async, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield |

##### 3. 데이터 타입(Data Type)

1. 숫자(Number) 타입

- int(정수, ingteger)

  - long은 없어짐
  - 8진수 : 0o / 2진수 : 0b / 16진수 : 0x 로 표현 가능
  - overflow가 없다.(임의 정밀도 산술 이용 : 남아있는 만큼의 가용 메모리를 모두 수 표현에 끌어다가 쓸 수 있음)

- float(부동소수점, 실수, floating point number)

  - 값을 비교하는 과정에서 오류가 생길 수 있다.

  - ```python
    a = 8.5 - 0.21
    b = 8.29
    a == b
    False
    # 다음의 방법들로 처리
    # 1. abs
    abs(a-b) <= 1e-10
    True
    # 2. sys // epsilon은 반올림 함으로써 발생하는 오차 상환
    import sys
    abs(a-b) <= sys.float_info.epsilon
    True
    # 3. math
    import math
    math.isclose(a, b)
    True
    ```

2. 글자(string) 타입

3. 참/거짓(Boolean) 타입

##### 4. 형변환(Type conversion, Typecasting)

1. 암시적 형변환(Implicit Type Conversion)
2. 명시적 형변환(Explicit Type Conversion)

##### 5. 연산자(Operator)

1. 산술 연산자
2. 비교 연산자
3. 논리 연산자
4. 복합 연산자
5. 기타 주요 연산자
6. 연산자 우선순위

##### 6. 참고

1. 표현식(Expression)
2. 문장(Statement)

