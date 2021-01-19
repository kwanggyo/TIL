## Python



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



#### 수업정리  - 00.Python_intro

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
     
     2 1
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
    print(a)
    8.28999999999999999
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

  - 컴퓨터식 지수 표현 방식 e or E

  - ```python
    pi = 3141592-6
    print(pi, type(pi))
    
    3.141592 <class 'float'>
  ```
    
  - round : 0 ~ 4는 내림, 짝수에서 5는 내림, 홀수에서 5는 올림, 6 ~ 9는 올림

    ```python
    round(5.5 - 3.22, 2)
    
    2.28
    ```

- complex(복소수, complex number)

  - 실수부와 허수부를 가진다.

  - 허수부는 j로 표현

  - 문자열을 변환할때, 문자열의 중앙의 연산자 주위에 공백을 포함해서는 안된다.

    ```python
    complex('5 + 5j')  #ValueError
    ```


2. 문자(string) 타입

- 기본 활용법

  - Single quotes(')나 Double quotes(")를 활용하여 표현
  - 문자열 안에 따옴표를 쓰려면 '안에  " or "안에 ' 를 활용하여 표현
  - PEP-8 : 하나의 문장부호를 선택하여 유지하도록 한다. 보통(')
  - 문자열은 +, * 연산이 가능, 변수화 사용 가능

- 이스케이프 시퀀스

  - | 문자 |       의미       |
    | :--: | :--------------: |
    |  \n  |     줄 바꿈      |
    |  \t  | 탭 만큼 띄어쓰기 |
    |  \r  |    캐리지리턴    |
    |  \0  |       Null       |
    | \\\  |      \ 출력      |
    | \\'  |      ' 출력      |
    | \\"  |      " 출력      |

  - end 옵션

    ```python
    print('안녕하세요.', end='!')
    print('반갑습니다.', end='!')
    
    안녕하세요!반갑습니다!
    ```

- String interpolation

  - %-formatting

  - str.format()

  - f-strings : python 3.6 이후 version

    ```python
    score = 4.5
    # %-formatting
    print('나의 학점은 %s 입니다.', % score)
    # str.format()
    print('나의 학점은 {} 입니다.', format(score))
    # f-strings
    print(f'나의 학점은 {score} 입니다.')
    
    나의 학점은 4.5 입니다.
    ```

  - 다양한 형식 활용

    - interpolation에서 출력형식 지정

      ```python
      import datetime
      today_now = datetime.datetime.now()
      print(today)
      
      2021-01.19 19:51:35.805035
              
      print(f'오늘은 {today:%y}년 {today:%m}월 {today:%d}일 {today:%A} 입니다.'   
            
      오늘은 21년 01월 19일 Tuesday 입니다.
      ```

    - interpolation에서 연산

      ```python
      pi = 3.141592
      print(f'원주율은 {pi:4}, 반지름이 4인 원의 넓이는 {pi*4*4}')
      
      원주율은 3.142, 반지름이 4인 원의 넓이는 50.265472
      ```

2. 참/거짓(Boolean) 타입
   - True와 False로 이루어짐
   - 비교/논리 연산을 수행
   - 0, 0.0, (), [], {}, '', None 은 False로 변환
   - 0이 아닌 나머지는 True
   - None 타입 : 값이 없음을 표현

##### 4. 형변환(Type conversion, Typecasting)

1. 암시적 형변환(Implicit Type Conversion)

   - 사용자가 의도하지 않았지만 파이썬 내부적으로 자동으로 형변환

   - bool, Numbers(int, float, complex) 에서만 가능

     ```python
     True + 5 = 6
     int_num = 5
     float_num = 10
     complex_num = 5+5j
     int_num + float_num = 15 <class 'float'>
     int_num + complex_num = 10+5j <class 'complex'
     ```

2. 명시적 형변환(Explicit Type Conversion)

   - 암시적 형변환이 아니면 모두 명시적으로 형변환 필요

   - 암시적으로 형변환 되는 모든 경우도 명시적 형변환 가능

     - int() : string, float => int
     - float() : string, float => float
     - str() : int, float, list, tuple, dictionary => str

   - string => integer : 형식에 맞는 숫자만 가능

   - integer => string : 모두 가능

     - 참고예제

       ```python
       aaa = '5.5'
       int(aaa) ## => float 형식이기 때문에 불가능
       bbb = 5.5
       int(aaa) # => 3 float은 int로 변환 가능
       ```

##### 5. 연산자(Operator)

1. 산술 연산자

   | 연산자 |   내용   |
   | :----: | :------: |
   |   +    |   덧셈   |
   |   -    |   뺄셈   |
   |   *    |   곱셈   |
   |   /    |  나눗셈  |
   |   //   |    몫    |
   |   %    |  나머지  |
   |   **   | 거듭제곱 |

   - 함수 divmod

     ```python
     quotient, remaider = divmod(5, 2)
     print(f'몫은 {quotient}, 나머지는 {remainder} 입니다.')
     
     몫은 2, 나머지는 1 입니다.
     ```

2. 비교 연산자

   | 연산자 |          내용          |
   | :----: | :--------------------: |
   |   <    |          미만          |
   |   <=   |          이하          |
   |   >    |          초과          |
   |   >=   |          이상          |
   |   ==   |          같음          |
   |   !=   |        같지않음        |
   |   is   |    객체 아이덴티티     |
   | is not | 부정된 객체 아이덴티티 |

3. 논리 연산자

   | 연산자  |             내용             |
   | :------ | :--------------------------: |
   | a and b |   a와 b 모두 True => True    |
   | a or b  |  a와 b 모두 False => False   |
   | not a   | True => False, False => True |

   - &와 | 는 비트 연산자

- 단축평가

  - 첫 번째 값이 확실하면 두 번째 값은 확인 하지 않음

  - 속도 향상

    ```python
    'x' and 'y' # y
    'x' or 'y' # x
    three_word = 'box'
    ('x' and 'y') in three_word  # False
    ('y' and 'x') in three_word  # True
    ('x' or 'y') in three_word  # True x
    ('y' or 'x') in three_word  # True x
    ```

    

4. 복합 연산자

   - 연산과 대입이 함께 이루어짐

   - 반복문에서 개수를 카운트 할 때, 주로 활용

     | 연산자  |    내용    |
     | :-----: | :--------: |
     | a += b  | a = a + b  |
     |  a -=b  | a = a - b  |
     | a *= b  | a = a * b  |
     | a /= b  | a = a / b  |
     | a //= b | a = a // b |
     | a %= b  | a = a % b  |
     | a **=b  | a = a ** b |

5. 기타 주요 연산자

- Concatenation

  - 숫자가 아닌 자료형은 + 연산자를 통해 합칠 수 있음

  ```python
  'he' + 'llo' # 'hello'
  
  [1, 2, 3] + [4, 5, 6] # [1, 2, 3, 4, 5, 6]
  ```

- Containment Test

  - in 연산자를 통해 요소가 속해있는지 여부 확인

- Identity

  - is 연산자를 통해 동일한 object 인지 확인

  - 참고예제

    ```python
    # 값은 같은데 object는 다름
    x = []
    y = []
    print(x == y, x is y)
    True False
    # 느낌표 때문에 다름
    x = 'hello!'
    y = 'hello!'
    print(x is b)
    False
    # 파이썬에서 -5 부터 256 까지의 id는 동일
    # id까지 같아야 object 판단에서 True가 나옴
    ```

- Indexing / Slicing

  - []를 통해 값에 접근하고 [:]를 통해 리스트를 Slicing

  - 참고예제

    ```python
    a = 'apple'
    #Indexing
    a[0]
    'a'
    #Slicing
    a[0:3]
    'app'
    ```

6. 연산자 우선순위

   - 괄호를 통해 입력하는 것 추천

     |  0   | Grouping () |
     | :--: | :---------: |
     |  1   |   Slicing   |
     |  2   |  Indexing   |
     |  3   |     **      |
     |  4   |  부호 +, -  |
     |  5   |   *, /, %   |
     |  6   |    +, -     |
     |  7   |   in, is    |
     |  8   |     not     |
     |  9   |     and     |
     |  10  |     or      |

##### 6. 참고

1. 표현식(Expression)

   - 하나의 값(value)으로 환원 될 수 있는 문장(boolean도 가능)
2. 문장(Statement)
   - 파이썬에서 실행 가능한 최소한의 코드 단위
   - 하나의 값(value), 표현식(Expression) 도 문장이 될 수 있음
   - 문장 집합안에 표현식 집합이 있음



#### 수업정리 - 01.Data_container

##### 컨테이너(Container)

: 여러 개의 값을 저장할 수 있는 것

##### 1. 시퀀스(sequence)형 컨테이너

: 데이터가 순서대로 나열된 형식

- 특징

  - 순서를 가질 수 있다.
  - 특정 위치의 데이터를 가리킬 수 있다.

- 종류

  - 리스트(list)

    - [], list()를 통해 만듬
    - 값에 대한 접근은 list[i]

    ```python
    # list 만들기
    menu = ['치킨', '피자', '족발']
    print(menu)
    print(menu[0])
    
    ['치킨', '피자', '족발']
    '치킨'
    ```

  - 튜플(tuple)

    - 수정 불가능, 불변(immutable), 읽기만 가능
    - 직접 사용보단 내부에서 다양한 용도로 활용

    ```python
    # tuple 만들기
    one_tuple = (1, 11)
    two_tuple = 2, 22
    o, t = 1, 2
    print((one_tuple), (two_tuple), (o, t))
    
    (1, 11), 2, 22, 1 2
    
    # 하나의 값을 가질 때
    first_tuple = ('hi',)
    print(type(first_tuple))
    print(len(first_tuple))
    
    <class 'tuple'>
    1
    
    # 변경 불가능, 읽을 수는 있음
    num_tuple = (1, 2)
    print(num_tuple[0])  # 1
    num_tuple[0] = '11'
    print(num_tuple)  ## 오류
    ```

  - 레인지(range)

    - 숫자의 시퀀스를 나타내기 위해 사용
    - range(n) : 0부터 n-1까지의 값을 가짐
    - range(n, m, s) : n부터 m-1까지 +s만큼 증가

    ```python
    # range 만들기
    range(5)
    print(range(5)) # range(0, 5)
    
    #list 값으로 바꿔서 확인
    list(range(5))
    print(range(5))  # [0, 1, 2, 3, 4]
    list(range(0, -5, -1))
    print(range(0, -5, -1))  # [0, -1, -2, -3, -4]
    ```

- 시퀀스에서 활용할 수 있는 연산자 / 함수

  - in, not in, +(concatenation), *n, s[i], s[i : j], s[i : j : k], len(), min(), max(), s.count(x) - x의 개수

##### 2. 비 시퀀스(Non-sequence)형 컨테이너

: 데이터가 순서없이 나열된 형식

- 종류

  - 셋(set)
    - 순서가 없고 중복된 값이 없다.
    - 빈 집합을 만들려면 set() 사용 ({}로는 불가능)

  ```python
  # set 
  set_2 = {2, 4, 6, 8}
  print(set_2)  # {2, 4, 6, 8}
  set_4 = {4, 8, 12, 16}
  
  # 차집합, 합집합, 교집합
  set_2 - set_4  # {2, 6}
  set_2 | set_4  # {2, 4, 6, 8, 12, 16}
  set_2 & set_4  # {4, 8}
  
  # 중복 불가
  {1, 1, 2, 2, 3, 4}  # {1, 2, 3, 4}
  
  # set을 활용한 list 중복값 제거
  my_list = [1, 2, 1, 3, 4, 2]
  list(set(my_list))  # [1, 2, 3, 4] - 순서가 보장되지 않음!
  ```

  - 딕셔너리(dictionary)

    - key와 value가 쌍으로 이루어져 있으며, 궁극의 자료 구조
    - key는 변경 불가능(immutable)한 데이터만 가능
    - value는 list, dictionary를 포함한 모든 것 가능
    - ()와 {}를 통해 비어있는 딕셔너리 만들기 가능
    - 중복된 key 존재할 수 없음

    ```python
    # dictionary 만들기
    region_num = {'서울': '02', '경기': '031', '대전': '042', '계룡': '042'}
    print(region_num['대전'])
    =>'042'
    
    region_num.keys()
    => dict_keys(['서울', '경기', '대전', '계룡'])
    
    region_num.values()
    region_num.values = region_num.values() # print 하는 법
    print(region_num.values)
    => dict_values(['02', '031', '042', '042'])
    
    region_num.items()
    => dict_items([('서울': '02'), ('경기': '031'), ('대전': '042'), ('계룡': '042')])
    
    list(region_num.items())[2]
    => ('대전', '042')
    
    type(list(region_num.items())[2])
    => tuple
    ```

##### 3. 컨테이너형 형변환

- 서로 변환 가능

  - string, list, tuple, set 은 서로 변환 가능

  - range와 dictionary 로는 불가능

  - 참고 예제

    ```python
    # list 형 변환
    l = [1, 2, 3]
    str(l)  # '[1, 2, 3]'
    tuple(l)  # (1, 2, 3)
    set(l)  # {1, 2, 3}
    range(l)  ## 오류
    dict(l)  ## 오류
    
    # range 형 변환
    r = range(1, 3)
    str(r)  # '[1, 2, 3]'
    list(r)  # [1, 2, 3]
    set(r)  # {1, 2, 3}
    tuple(r)  # (1, 2, 3)
    dict(r)  ## 오류
    
    # dictionary 형 변환
    d = {'mon': '8', 'day': 29}
    str(d)  # '{'mon': '8', 'day': 29}' 
    list(d)  # ['mon', 'day']
    tuple(d)  # ('mon', 'day')
    set(d)  # {'mon', 'day'}
    # list, tuple, set은 키만 모아서
    # 딕셔너리는 key를 통해서 value 에 접근한다.
    # key를 알려주면 value에 접근할 수 있음
    # value를 알려주면 그에 맞는 key는 찾을 수 없다.
    range(d)  ## 오류
    ```

##### 4. 데이터의 분류

: 하나의 값을 뽑아서 바꿀 수 있는 지에 따라 mutable과 immutable로 나뉜다.

- immutable

  - 변경 불가능
  - 숫자(Number), 글자(String), Boolean, range(), tuple(), frozenset()

- mutable

  - 변경 가능
  - list, dict, set

- 데이터 복사

  ```python
  # immutable
  n1 = 1
  n2 = n1 
  n2 = 2
  print(n1)  # 1
  print(n2)  # 2
  
  # mutable
  n1 = [1, 2, 3]
  n2 = n1
  n2[0] = 1000
  print(n1)  # [1000, 2, 3]
  print(n2)  # [1000, 2, 3]
  
  # 위에서 n2만 바뀌게 하려면 새로운 리스트를 만들어야함
  n1 = [1, 2, 3]
  n2 = list(n1)
  n2[0] = 100
  print(num1)  # [1, 2, 3]
  print(num2)  # [1000, 2, 3]
  ```

##### 5. 정리

- Sequence : String, list, tuple, range
- Non-Sequence : set, dictionary
- immutable : String, tuple, range
- mutable : list, set, dictionary



### 01.19

:memo: lab.ssafy

- 내 컴퓨터로 파일을 다운 받고 싶을 때 : git clone 뒤에 clone-HTTPS 주소
- pip pull origin master : 새로 업데이트할 때
- get remote -v : 현재 등록된 remote를 보여준다
- 유의사항 : 공유받은 handouts를 임의로 건들면 pull 할 때 문제가 발생할 수 있음
- 위치변경x, 수정x, 복사해서 사용



#### homework review

- 주피터에서는 맨 아래의 값을 보여줌(굳이 print할 필요 없음)
- 프로그래밍에서 num1 = num2 False 차이는 아주 작은 차이로 계산할 경우에는 가능
  - ex) 수학 공식은 천만건 중에 하나라도 예외가 있으면 안됨
  - ex) 공학에서 천만건 중에 1개 불량이면 좋은 것
- 필요하다면 출력 후 보정



#### 수업정리 - 02.control_flow





