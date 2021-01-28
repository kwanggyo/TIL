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
      print(today_now)
      
      2021-01.19 19:51:35.805035
              
      print(f'오늘은 {today_now:%y}년 {today_now:%m}월 {today_now:%d}일 {today_now:%A} 입니다.'   
            
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

     - int() : string, float를  int로 변환
     - float() : string, int를 float으로 변환
     - str() : int, float, list, tuple, dictionary를  str로 변환

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
     | a -= b  | a = a - b  |
     | a *= b  | a = a * b  |
     | a /= b  | a = a / b  |
     | a //= b | a = a // b |
     | a %= b  | a = a % b  |
     | a **= b | a = a ** b |

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

#### 제어문(Control Statement)

: 코드 실행의 순차적인 흐름을 제어

##### 1. 조건문(Conditional Statement)

if : 참 / 거짓을 판단할 수 있는 조건과 같이 사용되어야 한다.

- 들여쓰기를 유의하여 작성(PEP8에서는 4spaces 권장)

  ```python
  # 내 생일 출력
  birthday = input('날짜를 입력하세요 ex)02.27: ')
  print(birthday)
  
  if birthday == '08.29':
  	print('이광교님의 생일 입니다. 축하합니다.')
  else:
      print('이광교님의 생일이 아닙니다.')
  ```

  ```python
  # 홀수 / 짝수 판별
  # input은 str형이기 때문에 int로 형변환
  num = int(input('숫자를 입력하세요. : '))
  print(num)
  
  if num % 2:  # True = 1, False = 0 을 이용
      print('홀수')
  else:
      print('짝수')
  ```

- elif

  ```python
  # 점수에 따른 학점 출력
  score = int(input('점수를 입력하면 학점이 나옵니다.: '))
  if score >= 90:
      print('A')
      if score >= 95:
          print('A+')
  elif score >= 80:
      print('B')
  elif score >= 70:
      print('C')
  elif score >= 60:
      print('D')
  else:
      print('F')
  ```

- 조건 표현식

  ```python
  # 한줄에 표현
  # 0과 비교
  number = int(input('숫자를 입력하세요 : '))
  print('0보다 크다.') if num < 0 else print('0 보다 크지 않다.')
  ```

  

##### 2. 반복문(Loop Statement)

- while

  - 반드시 종료조건을 설정해야 함
  - 코드는 4spaces 들여쓰기

  ```python
  # 1에서 주어진 수까지의 합
  num = int(input())
  i = 1
  total = 0
  
  while i <= num:
      total += i
      i +=  1
  print(total)
  ```

  ```python
  # 주어진 수 거꾸로 한자리씩 출력
  number = int(input())
  print(number)
  while number > 0:
      print(number % 10)
      number = number // 10
  ```

- for

  ```python
  # range 출력
  for i in range(5):
      print(i)
      
  0, 1, 2, 3, 4
  ```

  ```python
  # 1 ~ 20 사이 홀수 출력
  for i in range(1, 20):
      if i % 2:
          print(i)
  ```

  ```python
  # 삼형제
  brother = ['이승교', '이광교', '이민교']
  for num in range(len(brother)):
      print(brother(num), num)
  
  이승교 1
  이광교 2
  이민교 3
  ```

  - enumerate

    - tuple 타입으로 돌려줌

    ```python
    # 점심 메뉴, 번호와 함께
    lunch = ['치킨', '피자', '짜장면', '계란밥']
    for menu in enumerate(lunch):
        print(menu)
    type(menu)
    
    (0, '치킨')
    (1, '피자')
    (2, '짜장면')
    (3, '계란밥')
    <class 'tuple'>
    
    # 다르게 표현, start를 사용하면 1부터 카운트
    for idx, menu in enumerate(lunch, start=1):
        print(idx, menu)
        
    1 치킨
    2 피자
    3 짜장면
    4 계란밥
    ```

    

##### 3. 반복제어

- break

  - for 나 while 문에서 빠져나간다.

  ```python
  # for 문
  for i in range(7):
      if i == 5:
          break
      print(i, end=' ')
  
  0 1 2 3 4
  
  # while 문
  n = 0
  while True:
      if n == 5:
          break
      print(n, end=' ')
      n += 1
    
  0 1 2 3 4
  
  # 쌀보리 게임
  rice = ['보리', '보리', '쌀', '보리']
  for seed in rice:
      print(seed)
      if seed == '쌀':
          print('잡았다!!')
          break
          
  보리
  보리
  쌀
  잡았다!!
  ```

- continue

  - continue 이후의 코드를 수행하지 않고 다음 요소 부터 계속하여 실행한다.

  ```python
  # 범위 안의 홀수 출력
  for i in range(6):
      if i % 2 == 0:
          continue  # 반복문 안에 있는 같은 수준의 코드를 건너뜀
      print('{}는 홀수이다', format(i))
  print('반복문 끝')
  
  1는 홀수이다
  3은 홀수이다
  5는 홀수이다
  반복문 끝
  
  # 리스트 활용, 성인 구별
  ages = [15, 27, 9, 32, 28, 30]
  for age in ages:
      if age < 20:
          continue  # if else를 써도 상관없음(취향차이)
      print(f'{age}살은 성인입니다.')
      
  27살은 성인입니다.
  32살은 성인입니다.
  28살은 성인입니다.
  30살은 성인입니다.
  ```

- for - else

  - 끝까지 반복문을 실행한 후 실행
  - 반복문이 break 로 종료될 때는 실행되지 않음
  - 반복에서 리스트 소진(for)이나 조건이 거짓(while)이 되어 종료할 때 실행

  ```python
  # break 실행 안될 때
  for num in range(5):
      print(num)
      if num == 10:
          break
  else:  # for 위치에
      print('break 실행 안됨')  # 중간에 break가 되면 실행되지 않음
      
  # list 예제
  my_list = [2, 3, 5, 8, 13]
  for num in my_list:  
      print(num)
      if number == 7:
          print(True)
          break
  else:
      print(False)
  
  2
  3
  5
  8
  13
  False
  ```

  

- pass 

  - 아무것도 하지 않음
  - 문법적으로 문장이 필요하지만 특별히 할 일이 없을 때, 자리를 채우는 용도로 사용

  - 코딩 중에 실행 결과 확인 하고 싶을 때 사용

  ```python
  # 코딩 중 실행 결과 확인
  my_list = [2, 3, 5, 8, 13]
  for num in my_list:
      if number == 5:
          pass
      print(num)
      
  2
  3
  5
  8
  13
  
  # continue와 차이점
  my_list = [2, 3, 5, 8, 13]
  for num in my_list:
      if number == 5:
          continue
      print(num)
     
  2
  3
  8
  13
  ```

  

### 01.20

#### 수업정리 - 03.function_1

#### 함수

- 특정한 기능을 하는 코드의 묶음
- 사용하는 이유
  - 높은 가독성(코드가 짧아짐)
  - 재사용성
  - 유지보수(분리되어 있어서 기능 수정이 편리함)

##### 1. 선언과 호출

- 선언 : def 함수이름(매개변수): , 4spaces 들여쓰기

- 동작 후에 return을 통해 결과값을 전달할 수 있다.

- return 값이 없으면, None을 반환

- 호출 : 함수이름(인자)

  ```python
  # 두 수의 합을 계산하는 함수
  def my_sum(a,b):  # 함수 선언
      return a + b
  number = my_sum(2, 9)  # 함수 호출
  print(number)  # 11
  print_number = print(number)  # 11
  print(print_number)  #None
  ```

##### 2. Output

- 오직 한 개의 객체만 반환

- return a, b 와 같이 사용 가능, tuple형으로 return

- return이 없으면 None으로 반환

  ```python
  # tuple형 return
  def my_hello(name):
      return 'hello', name
  hello = my_hello('이광교')
  print(hello, type(hello))
  
  ('hello', '이광교'), <class 'tuple'>
  ```

  ```python
  # 정렬 함수
  my_list = [5, 3, 7, 1]
  print(my_list)  # [5, 3, 7, 1]
  a = [5, 1, 3, 2]
  b = a.sort()  # 원본을 바꿔버리고, return이 값이 없음
  print(a)  # 원본 리스트
  print(b)  # a.sort() 정렬 함수의 결과
  [1, 3, 5, 7]
  None
  
  a = [5, 1, 3, 2]
  b = sorted(a)  # 원본은 변화X, return으로 정렬
  print(a)  # 원본 리스트
  print(b)  # sorted(a) 결과
  [5, 3, 7, 1]
  [1, 3, 5, 7]
  ```

  ```python
  # 리스트의 합이 큰 리스트를 반환하는 함수
  def list_better(a, b):
      if sum(a) > sum(b):  # 더한 값을 비교, 내장함수 sum()
          return a
      else:
          return b
  print(list_better([10, 7], [15, 3]))
  [15, 3]
  ```

##### 3. Input

- 매개별수(parameter)

  - 입력을 받아 함수 내부에서 활용하는 '변수'
  - 정의할 때 사용

- 인자(argument)

  - 실제로 전달되는 입력값

  - 호출할 때 사용

  ```python
  # tuple형 return - 위의 예제
  def my_hello(name):  # name : 매개변수
      return 'hello', name
  hello = my_hello('이광교')  # 이광교 : 인자
  print(hello, type(hello))
  
  ('hello', '이광교'), <class 'tuple'>
  ```

  - 위치인자
  - 기본인자
  - 키워드인자

  ```python
  # 인자 순서
  def hello(name='익명', age):  ## Error 기본 인자 뒤에 위치 인자 불가
  # name='익명' : 기본 인자, age : 위치 인자
  def hello(age, name='익명'):
      print(f'안녕? 난 {name}, {age}살이야')
  hello(27)  # 안녕? 난 익명, 27살이야
  hello(100, '광교')  # 안녕? 난 광교, 100살이야
  hello(name='이광교', age=27)  # 안녕? 난 이광교, 27살이야
  # name='이광교', age=27 : 키워드 인자
  hello(age=3000, '곰')  ## Error 키워드 인자 후 위치 인자 활용 불가
  ```

  - 가변 인자 리스트
    - 개수가 정해지지 않은 임의의 인자를 받기 위해서 list 활용
    - 보통 변수명을 args로 하고 tuple형태로 처리됨
    - *args

  ```python
  # 가변 인자 리스트
  def daejeon1_students(*args):
      print(args)
      print(type(args))
  daejeon1_students('형식', '덕영', '광교')
  ('형식, '덕영', '광교')
   <class 'tuple'>
   
   # 가변 이후의 변수는 키워드 인자를 활용해야함
   def daejeon1_students(*args, prof):
   	for student in args:
      	print(args)
      print(f'대전 1반 교수님 {prof}')
  daejeon1_students('형식', '덕영', '광교') ## Error prof를 정해줘야함
  daejeon1_students('형식', '덕영', '광교', prof='빈산')
  ('형식, '덕영', '광교')
   대전 1반 교수님 빈산
  ```

  - 가변 키워드 인자
    - 정해지지 않은 키워드 인자들은 dict으로 처리
    - 보통 변수를  kwargs로 사용
    - **kwargs
    - 반드시 맵핑을 해서 넣어야함

  ```python
  # menu
  def menu_dict(**kwargs):
      print(kwargs)
      print(type(kwargs))
      return kwargs
  print(menu_dict(아침='토스트', 점심='계란밥', 저녁='고기'))
  # 반드시 맵핑 필요
  {'아침': '토스트', '점심': '계란밥', '저녁': '고기'}
  
  # 인자는 숫자만으로 이루어질 수 없음 -> 키워드 인자로 넘기면 함수에서 식별자로 사용
  dict(1='1, 2='3', 3='2') ## Error
  dict(((1, 1), (2, 3), (3, 2))) # 해결
  ```

  

#### 수업정리 - 04.function_2

##### 1. 함수와 스코프(scope)

- 함수는 코드 내부에 공강(scope)를 생성
- 생성된 공간은 지역 스코프(local scope), 그 외의 공간은 전역 스코프(global scope)

- 이름검색규칙

  - LEGB Rlue
    - Local scope : 정의된 함수
    - Enclosed scope : 상위 함수
    - Global scope : 함수 밖의 변수 혹은 import 모듈
    - Built-in scope : 파이썬안에 내장되어 있는 함수

  ```python
  # LEGB Rule
  a = 100 # G
  b = 200 # G
  def enclosed():
      a = 300  
      # Enclosed 함수 입장에서는 local, local 함수 입장에서는 Enclosed
      def local():
          c = 400  # local
          print(a, b, c)
      local()
      a = 500  
      # Enclosed 함수 입장에서는 local, local 함수 입장에서는 Enclosed
  enclosed()
  # 여기까지 a = 300, b = 200, c = 400
  ```

##### 2. 재귀 함수(recursive funtion)

- 함수 내부에서 자기 자신을 호출하는 함수
- 알고리즘을 설계 및 구현하는데 활용

- 팩토리얼 계산

  ```python
  # Factorial
  def factorial(n):
      if n == 1:
          return 1
      else:
          return n * factorial(n-1)
  ```

- 피보나치 수열

  ```python
  # Fibonacci 수열
  # n 이 0이나 1일 때는 값도 0, 1이기 때문에 그대로 반환하면 되고, 
  # 2 이상일 때만 재귀 함수 두개로 분기해서 반환
  def fib(n):
      if n == 0:  # base case!
          return 0 
      elif n < 2:  # base case!
          return 1
      else:
          return fib(n-1) + fib(n-2)
  ```

- 반복문과의 차이

  - 장점
    - 코드의 가독성이 높아질 수 있다.
    - 작성이 간편해질 수 있다.

  - 단점

    - 반복문보다 메모리를 많이 사용한다

      (반복문은 사용 후 메모리를 반환 하는데, 재귀함수는 함수가 종료되기 전에 다시 호출하기 때문에 맨마지막 리턴될 때까지 메모리를 가지고 있다.)

    - 시간이 더 오래 걸릴 수 있다.

    - 반드시 base case가 존재해야한다. (최대 재귀 깊이)



### 01.21

#### 수업정리 -05.erroe_exception

#### 에러

##### 1. 문법 에러(Syntax Error)

- EOL : end of line // ex) 따옴표 오류

- EOF : end of file // ex) 괄호 닫기 오류

- 오류 line을 잘 봐야함

- 예외(Exception)

  - 문법적으로는 옳지만 실행시 발생하는 에러

  ```python
  # example
  
  # ZeroDivisionError : 0으로 나누기
  # NameError : 정의되지 않은 변수를 호출
  # TypeError : 자료형 타입 오류, 인자 적음/많음 오류, 자료 값 오류
  # ValueError : 존재하지 않는 값을 찾을 경우
  # IndexError : 존재하지 않는 index 조회, 비어있는 리스트 index 접근
  # KeyError : 딕셔너리에서 Key가 없는 경우
  # ModuleNotFoundError : 모듈을 찾을 수 없는 경우
  # ImportError : 모듈은 찾았으나 가져오는 과정에서 실패
  # KeyboardInterrupt : 사용자가 의도적으로 멈췄을 때(ctrl+c)
  ```

##### 2. 예외 처리Excepting Handling

- try & except

  - try 아래의 code block 실행
  - 예외 발생 X -> except 없이 실행 종료
  - 예외 발생 O -> 남은 부분을 수행하지 않고 except 실행

  ```python
  # ZeroDivisionError
  try:
      num1 = int(input('나눌 숫자(분자)를 입력하세요: '))
      num2 = int(input('나누는 숫자(분모)를 입력하세요: '))
      result = num1 / num2
  except ZeroDivisionError:  # 특정에러 처리
      print('0으로는 나누면 안됩니다')
  # 이게 없으면 ZeroDivisionError 일때 죽음
  ```

- as

  ```python
  try:
      <코드 블럭 1>
  except 예외 as err:
      <코드 블럭 2>
  # IndexError
  try:
      my_list = []
      print(my_list[-3])
  except IndexError as err:
      print(f'{err}, 오류가 발생했습니다.')
  list index out of range, 오류가 발생했습니다.
  ```

- 복수개의 예외처리

  - 하나 이상의 예외를 모두 처리 가능
  - 괄호가 있는 tuple로 여러 개의 예외 지정
  - 에러가 순차적으로 수행됨으로, 가장 작은 범주부터 시작

  ```python
  try:
      <코드 블럭 1>
  except (예외1, 예외2):
      <코드 블럭 2>
  ```

- else

  - 에러가 발생하지 않는 경우 수행되는 문장
  - 모든 except절 뒤에 와야함

- finally

  - 반드시 수행해야 하는 문장에 활용
  - 예외 발생 여부와 관계없이 try 문을 떠날 때 항상 실행
  - ex) DB에서 데이터를 가져올 때 오류 발생, finally : DB 종료

##### 3. 예외 발생 시키기(Excepting Raising)

- raise
  - 에러 발생시 사용자에게 선택할 수 있도록 함
  - ex) ZeroDivisionError 일 때, 다시 넣을지, 값이 무한대로 나오게 할지 선택
- assert
  - 상태를 검증하는데 사용
  - 무조건 AssertionError 발생
  - 검증식이 거짓일 경우 발생, 일반적으로 디버깅 용도로 사용



### 01.22

#### PJT

- 일정한 기간 안에 일정한 목적을 달성하기 위해 수행하는 업무의 묶음
- 정해진 기간, 금액, 인력 등 일정한 제약조건 하에서 각종 요구사항을 수행하는 방식



:memo: 기타

- dict와 json 은 jpg와 png 같은 관계 - 사용하는 목적은 같음
- load : 인코딩과 같은 역할, json 파일을 객체로 변환
  - 인코딩 : 사용할 수 있게 데이터 구조를 바꾸어줌
  - 일반적으로 utf-8 사용
- Key 사용 방식
  - 대괄호 접근['key값']
  - method.get('key값')



:point_right: 구글링을 통해 문서를 찾을 때는 docs.python.org 문서 추천(파이썬 공식 문서)



### 01.23

:chart_with_upwards_trend: 문제 풀이 feedback

- 어떻게 풀지 먼저 생각하고 글로 써본 후 코딩으로 구현!
- range의 slicing은 , 로 list의 slicing은 : 로 구분
- 값을 대입하는 경우 동시에 일어나야 할 때는 같은 줄에 써야함!  그렇지 않으면 순서가 생겨서 값이 달라짐
- for 문을 2개이상 써서 비교할 때에는 상위 for 문의 인덱스 값과 비교를 하는지 생각하고 비교 안할시 if 문을 통해 continue를 시켜줌
- for i in len() : type 오류가 뜸, 값을 집어넣어주어야 하기 때문에 range를 써야함



### 01.24

:chart_with_upwards_trend: 문제 풀이 feedback

- dict에서 key 값을 입력할때는 [] 사용
- 중첩 조건문에서는 앞에 return 을 썼으면 뒤에는 안써도 됨
- list로 형태 변환은 my_list = [result] 이런식으로!



## 01.25

### 데이터 구조(data_structure)_1

: 데이터를 편리하게 접근하고, 변경하기 위해서 데이터를 저장하거나 조작하는 방법

- 알고리즘 : String, List
- 데이터 구조 : Built-in Function

#### 1. Stiring

: immutable, ordered, iterable // 변경x, 순서o, 반복 가능

**1-1 조회 / 탐색**

- .find(x)

  : x의 첫 번째 위치를 반환, **없으면 -1 반환**

  ```python
  b = 'banana'
  b.find('x')
  ## = 0
  b.find('n')
  ## = 2
  b.find('g')
  ## = -1
  ```

- .index(x)

  : x의 첫 번째 위치를 반환, **없으면 오류 발생**

  ```python
  b = 'banana'
  b.index('x')
  ## = 0
  b.index('n')
  ## = 2
  b.find('g')
  ## = 오류 ValueErrorreplace
  ```

**1-2 값 변경**

- .replace(old, new[, count])

  : 바꿀 대상 글자를 새로운 글자로 바꿔서 변환, count 지정시 해당 개수만큼 시행

  ```python
  h = 'hello'
  h.replace('l', '')
  ## = 'heo'
  h.replace('l', '', 1)
  ## = 'helo'
  'hello'.replace('l', '', 2)
  ## = 'heo'
  ```

- .strip([chars])

  : 특정한 문자들에서서 양쪽을 제거하거나 왼쪽(lstrip), 오른쪽(rstrip)을 제거, 지정하지 않으면 공백을 제거

  - 데이터를 처리할 때 많이 사용
  - 가운데 공백은 제거할 수 없음
  - ex) 회원가입시 - 실수로 공백을 침 - 공백이 있다고 알려줌 or 알아서 없애줌

  ```python
  w = '  wowww!\t'
  w.strip()
  ## = 'wowww!'
  w.lstrip()
  ## = 'wowww!\t'
  w.rstrip()
  ## = '   wowww!'
  escape = '\n\t'
  escape.strip()
  ## = ''
  ```

- .split()

  : 문자열을 특정한 단위로 나누어 리스트로 반환

  - 사용 빈도가 높음
  - (,)에서 ,는 구분자
  - 기본은 공백을 기준

  ```python
  me = '이광교, 27, 01012345678'
  me.split(','), type(me.split(','))
  ## = ['이광교', '27', '01012345678'], list
  birth = '0 8 2 9'
  birth.split()
  ## = ['0', '8', '2', '9']
  ```

- 'seperator'.join(iterable)

  : 특정한 문자열로 만들어 반환

  반복가능한 컨테이너의 요소들을 separator를 구분자로 합쳐 (join()) 문자열로 반환

  ```python
  hi = '안녕하세요'
  '!'.join(hi)
  ## = '안!녕!하!세!요'
  hello = ['hi','안녕하세요']
  ','.join(hello)
  ## = 'hi,안녕하세요'
  ```

**1-3 문자 변형**

- .capitalize()

  : 앞 글자를 대문자로 만들어 변환

  ```python
  name_hi = 'lEE kWANGGYO, hI!'
  name_hi.capitalize()
  ## = 'Lee kwanggyo, hi!''
  ```

- .title()

  : 어포스트로피나 공백 이후를 대문자로 만들어 변환

  ```python
  name_hi = 'lEE kWANGGYO, hI!ee'
  name_hi.title()
  ## = 'Lee Kwanggyo, Hi!Ee'
  ```

- .upper()

  : 모두 대문자로 만들어서 반환

  ```python
  name_hi = 'lEE kWANGGYO, hI!ee'
  name_hi.upper()
  ## = 'LEE KWANGGYO, HI!EE'
  ```

- .lower()

  : 모두 소문자로 만들어서 반환

  ```python
  name_hi = 'lEE kWANGGYO, hI!ee'
  name_hi.lower()
  ## = 'lee kwanggyo, hi!ee'
  ```

- .swapcase()

  : 대 < - >소문자로 변경하여 반환

  ```python
  name_hi = 'lEE kWANGGYO, hI!ee'
  name_hi.swapcase()
  ## = 'Lee Kwanggyo, Hi!EE'
  ```

**1-4 기타 문자열 검증 : 참 / 거짓**

- .isalpha()

  : 문자열 내의 모든 문자가 알파벳이고, 적어도 하나의 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

  ```python
  '안녕'.isalpha()  ## T
  'hi'.isalpha()  ## T
  '안녕1'.isalpha()  ## F
  '1'.isalpha()  ## F
  ''.isalpha() ## F
  ','.isalpha() ## F
  ```

- .isdecimal()

  : 문자열 내의 모든 문자가 십진수 문자이고, 적어도 하나의 문자가 존재하는 경우 `True` 를 돌려주고, 그렇지 않으면 `False`

  ```python
  '3.5'.isdecimal()  ## F
  '3'.isdecimal()  ## T
  ```

- .isdigit()

  : 문자열 내의 모든 문자가 디짓이고, 적어도 하나의 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

  십진수 문자와, 위 첨자 숫자 등 특수 처리가 필요한 숫자 포함

- .isnumeric()  # 모르겠음

  : 문자열 내의 모든 문자가 숫자이고, 적어도 하나의 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

  숫자는 디짓과 유니코드 숫자 값 속성을 갖는 모든 문자

- .isspace()  # 모르겠음

  : 문자열 내에 공백 문자만 있고, 적어도 하나의 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

- .isupper()

  : 문자열 내의 모든 케이스 문자가 대문자이고, 적어도 하나의 케이스 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

- .islower()

  : 문자열 내의 모든 케이스 문자가 소문자이고, 적어도 하나의 케이스 문자가 존재하는 경우 `True`를 돌려주고, 그렇지 않으면 `False`

- .istitle()

  : 문자열이 제목 케이스 문자열이고 하나 이상의 문자가 있는 경우 `True` 그렇지 않은 경우는 `False`



#### 2. List

: mutable, ordered, iterable // 변경o, 순서o, 반복 가능

**2.1 값 추가 및 삭제**

- .append(x)

  : list에 값을 추가

  ```python
  fruits = ['apple', 'banana', 'grape']
  fruits.append('pineapple')
  print(fruits)  ## ['apple', 'banana', 'grape', 'pineapple']
  ```

- .extend(iterable)

  : list에 iterable(list, range, tuple, string) 값 추가

  []에 넣어서 추가해야함

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.append(['pineapple', 'melon'])
  print(fruits)  
  ## ['apple', 'banana', 'strawberry', 'pineapple', 'melon']
  fruits.append('grape')  # string 주의!
  print(fruits)
  ## ['apple', 'banana', 'strawberry', 'pineapple', 'melon', 'g', 'r', 'a', 'p', 'e']
  ```

:ballot_box_with_check: .append는 하나(''), .extend는 여러개([''])를 추가할 수 있다.

- .insert(i, x)

  : i 위치에 x 값을 추가

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.insert(2, '바나나')
  print(fruits)  ## ['apple', '바나나', 'strawberry']
  # i = -1에 넣으면 len(fruits)-1 위치에 들어감
  # 마지막에 넣고 싶으면 i = len(fruits) or 엄청 큰 숫자
  ```

- .remove(x)

  : list에서 값이 x인 것을 1개씩 삭제(순서대로), 삭제할 값이 없으면 오류 발생

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.remove('banana')
  print(fruits)  ## ['apple', 'strawberry']
  ```

- .pop(i)

  : i 위치의 값을 삭제하고 그 항목을 반환, i가 지정되지 않으면 마지막 항목 삭제 후 반환

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.pop(0)  # 여기서 이미 apple이 사라짐
  # 출력하고 싶으면 변수에 저장해서 그 변수를 출력!
  print(fruits.pop(0))  ## banana
  print(fruits)  ## ['strawberry']
  ```

- .clear()

  : list의 모든 항목을 삭제

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.clear()
  print(fruits)  ## []
  ```


**2.2 탐색 및 정렬**

- .index(x)

  : x 값에 해당하는 index 값을 반환(첫 번째 값), 없을 시 오류 발생

  ```python
  numbers = [1, 2, 3, 4, 5, 1]
  a.index(a) ## a
  ```

- .count(x)

  : 원하는 값의 개수를 확인

  ```python
  numbers = [1, 3, 1, 3, 2, 4, 2, 4, 1]
  numbers.count(1)  ##3
  ```

- .sort()

  : 오름차순으로 정렬, 원본 list를 변형 시키고 None을 return

- .sorted()

  : 오름차순으로 정렬, 원본은 보존하고 변형시킨 list를 return

  ```python
  numbers = [3, 1, 2, 5, 4]
  # sorted
  print(sorted(numbers))  ## [1, 2, 3, 4, 5]
  print(numbers)  ## [3, 1, 2, 5, 4]
  # sort
  print(numbers.sort())  ## None
  print(numbers) ## [1, 2, 3, 4, 5]
  # lotto
  import random
  sorted(random.sample(range(1, 46), 6))
  ## [11, 17, 18, 31, 38, 42]
  ```

- .reverse

  : 반대로 뒤집어줌

  ```python
  fruits = ['apple', 'banana', 'strawberry']
  fruits.reverse()
  print(fruits) ## ['strawberry', 'banana', 'apple']
  ```

**2.3 리스트 복사**

- 대입하여 복사하는 경우

  ```python
  a = [1, 2, 3, 4, 5]
  b = a
  a[0] = 5
  print(a)  ## [5, 2, 3, 4, 5]
  print(b)  ## [5, 2, 3, 4, 5]
  # 같은 주소(메모리)값을 가르키고 있기 때문에 같이 변한다.
  print(id(a)) ## 2123084223680
  print(id(b)) ## 2123084223680
  ```

- slice[:] 활용

  ```python
  a = [1, 2, 3, 4, 5]
  b = a[:]
  b[0] = 100
  print(a)  ## [1, 2, 3, 4]
  print(b)  ## [100, 2, 3, 4]
  ```

- list() 활용

  ```python
  a = [1, 2, 3, 4, 5]
  b = list(a)
  b[0] = 100
  print(a)  ## [1, 2, 3, 4]
  print(b)  ## [100, 2, 3, 4]
  ```

- 2차원 배열 복사 - deep copy

  : 깊은 복사 사용 필요 : 내부에 있는 모든 객체까지 값이 변경

  ```python
  # list 복사
  a = [[1, 2, 3], 4, 5]
  b = list(a)  # [주소,4,5]
  print(a, b)  ## [[1, 2, 3], 4, 5] [[1, 2, 3], 4, 5]
  b[0][0] = 100  # 내부에 있는 list는 같음
  print(a, b)  ## [[100, 2, 3], 4, 5] [[100, 2, 3], 4, 5]
  b[2] = '복사'
  print(a, b)  ## [[100, 2, 3], 4, 5] [[100, 2, 3], 4, '복사']
  
  # 깊은 복사(deep copy)
  import copy
  a = [[1, 2, 3], 4, 5]
  b = copy.deepcopy(a)
  print(a, b)  ## [[1, 2, 3], 4, 5] [[1, 2, 3], 4, 5]
  b[0][0] = 100
  print(a, b)  ## [[1, 2, 3], 4, 5] [[100, 2, 3], 4, 5]
  ```

**2.4 List Comprehension**

- 표현식과 제어문으로 list 생성

- 코드를 줄일 수 있음

- ```python
  [expression for 변수 in iterable]
  ```

  ```python
  numbers = [1, 2, 3, 4, 5]
  [number**3 for number in numbers]  ## [1, 8, 27, 64, 125]
  
  # 3.1 map 활용
  def cube(n):
      return n ** 3
  	list(map(cube, numbers))  ## [1, 8, 27, 64, 125]
  ```

**2.5 List Comprehension + 조건문**

: 조건문에 참인 식으로 list 생성

- ```python
  [expression for 변수 in iterable if 조건식]
  [expression if 조건식 else 식 for 변수 in iterable]
  ```

  ```python
  # 홀수 list
  numbers = [1, 2, 3, 4, 5]
  [number for number in numbers if number % 2 == 1]  ## [1, 3, 5]
  ```



### 3. Built-in Function

: iterable(list, dict, set, str, byte, tuple, range)한 데이터 구조에 적용 가능 

**3.1 map(function, iterable)**

- iterable한 구조의 모든 요소에 function을 적용한 후 결과를 돌려줌

- return은 map_object 형태

  ```python
  # '12345' 만들기
  # List Comprehension + .join()
  numbers = [1, 2, 3, 4, 5]
  [str(number) for number in numbers] ## ['1', '2', '3', '4', '5']
  ''.join[str(number) for number in numbers]  ## '123'
  
  # map
  map(str, numbers)  ## <map at 0x1ee51bd0790>
  list(map(str, numbers))  ## ['1', '2', '3', '4', '5']
  # str 부분에는 만들어준 함수를 넣어도 됨
  ```

**3.2 filter(function, iterable)**

- iterable에서 function의 반환된 결과가 True인 것들만을 구성하여 반환

- return은 filter_object 형태

  ```python
  def num(n):
      return n
  numbers = [0, 0.1, 1, 2, 3, 'hello', '', True, False, []]
  new_numbers = list(filter(num, numbers))
  print(new_numbers)  ## [0.1, 1, 2, 3, 'hello', True]
  # 0은 boolean으로 봤을 때 False의 값을 가지므로 반환 안함
  ```

**3.3 zip(*iterables)**

- 복수의 iterable 객체를 모아줌

- return은 zip_object 형태(튜플의 모음으로 구성) 

  ```python
  name = ['승', '광', '민']
  age = [28, 27, 23]
  sum = list(zip(name, age))
  print(sum)  ## [('승', 28), ('광', 27), ('민', 23)]
  ```

  

### 데이터 구조(data_structure)_2

#### 1. Set

: mutable, unordered, iterable // 변경o, 순서x, 반복 가능

**1.1 추가 및 삭제**

- .add(elem)

  : elem을 세트에 추가

  ```python
  fruits = {'apple', 'banana', 'strawberry'}
  fruits.add('grape')
  print(fruits)  ## {'apple', 'banana', 'strawberry', 'grape'}
  ```

- .update(*others)

  : 여러가지 값을 추가, 인자로는 반드시 iterable 데이터 구조를 전달해야함

  ```python
  fruits = {'apple', 'banana', 'strawberry'}
  fruits.update(('grape', 'pineapple'))
  print(fruits)  ## {'strawberry', 'apple', 'banana', 'pineapple', 'grape'}
  ```

- .remover(elem)

  : elem을 세트에서 삭제, 없으면 KeyError 발생

  ```python
  fruits = {'apple', 'banana', 'strawberry'}
  fruits.remove('apple')
  print(fruits)  ## {'banana', 'strawberry'}
  ```

- .discard(elem)

  : elem을 세트에서 삭제, 없어도 에러가 발생 안함

  ```python
  fruits = {'apple', 'banana', 'strawberry'}
  fruits.discard('pineapple')
  print(fruits)  ## {'apple', 'banana', 'strawberry'}
  ```

- .pop()

  : 임의의 원소를 제거해서 반환

  ```python
  fruits = {'apple', 'banana', 'strawberry'}
  fruits.pop()
  print(fruits)  ## {'banana', 'strawberry'} reset 후 다시 하면 바뀜
  ```

:ballot_box_with_check: list.pop(i)는 i or 마지막 원소를 제거한다. list /set - ordered / unordered

​	

#### 2. Dictionary

: mutable, unordered, iterable // 변경o, 순서x, 반복 가능

**2.1 조회**

- .get(ket[, default])

  : ket를 통해 value를 가져옴

  default는 기본적으로 None이기 때문에 KeyError가 발생하지 않음

  ```python
  fruits_dict = {'사과': 'apple', '바나나': 'banana', '딸기': 'strawberry'}
  fruits_dict.get('멜론')  ## None
  fruits_dict.get('멜론', 3)  ## 3
  fruits_dict.get('사과')  ## apple
  ```

**2.2 추가 및 삭제**

- pop(key[, default])

  : key가 dictionary에 있으면 제거하고 그 값을 돌려줌, 그렇지 않으면 default 반환

  default가 없는 상태에서 dictionary에 없으면 KeyError 발생

  ```python
  fruits_dict = {'사과': 'apple', '바나나': 'banana', '딸기': 'strawberry'}
  fruits_dict.pop('멜론')  ## 오류
  fruits_dict.pop('멜론', 3)  ## 3
  fruits_dict.pop('사과')  ## apple
  ```

- update()

  : 값을 제공하는 key, value로 덮어씁니다.

  ```python
  fruits_dict = {'사과': 'apple', '바나나': 'banana', '딸기': 'strawberry'}
  fruits_dict.update({'사과': 'AAAplle'})
  fruits_dict.update({'바나나': 'BBBanana'})
  fruits_dict ## {'사과': 'AAAplle', '바나나': 'BBBanana', '딸기': 'strawberry'}
  ```

**2.3 딕셔너리 순회**

- keys(), values(), items()

  ```python
  fruits_dict = {'사과': 'apple', '바나나': 'banana', '딸기': 'strawberry'}
  print(fruits_dict.keys())  ## dict_keys(['사과', '바나나', '딸기'])
  print(fruits_dict.values())  ## dict_values(['apple', 'banana', 'strawberry'])
  print(fruits_dict.items())  ## dict_items([('사과', 'apple'), ('바나나', 'banana'), ('딸기', 'strawberry')])
  # 활용
  for fruit in fruits_dict.values():
      print(fruit)  
      ## apple
  	## banana
  	## strawberry
  # 참고 : 그냥 for문을 돌리면 key 값들이 나옴
  fruits_dict = {'사과': 'apple', '바나나': 'banana', '딸기': 'strawberry'}
  for fruit in fruits_dict:
      print(fruit)
      ## 사과
      ## 바나나
      ## 딸기
  ```

**2.4 Dictionary comprehension**

- iterable에서 dict을 생성 가능

  ```python
  {key: value for 요소 in iterable}
  
  dict({key: value for 요소 in iterable})
  ```

  ```python
  numbers = [1, 2, 3, 4 ,5]
  {str(n) : n for n in numbers}
  ## {'1': 1, '2': 2, '3': 3, '4': 4, '5': 5}
  ```

**2.5 Dictionary comprehension + 조건**

- 조건문에 참인 식으로 dictionary 생성

  ```python
  {key: value for 요소 in iterable if 조건식}
  
  {key: value if 조건식 else 값 for 요소 in iterable}
  ```



## 01.26

### 모듈(Module)

: 특정 기능을 하는 코드를 담고 있는 파일(스크립트)

#### 1. 모듈 생성

- New -> Text File 생성 후 .py로 저장

#### 2. 모듈 활용

- 모듈 활용을 위해서는 반드시 ``import``를 통해 내장 모듈을 이름 공간으로 가져와야함
- 함수를 자주 사용할 것이라면 변수에 할당해서 사용 가능



### 패키지(Package)

: 점(.)으로 구분된 모듈 이름을 써서 모듈을 구조화하는 방법

#### 1. 패키지 생성

- New -> Folder 생성 후 아래의 폴더구조 생성

  ```python
  my_package/ 
      __init__.py
      math/
          __init__.py
          tools.py 
  # 모듈 이름 my_package.math는 my_package라는 이름의 패키지에 있는 math라는 이름의 하위 패키지를 가리킴
  # __init__.py 3.3 이후 버전은 없어도 패키지로 인식, 호환을 위해 쓰는 것을 권장 // __init__.py 파일은 비워두어야함
  ```

#### 2. 패키지 활용

- `from`과 `import` 를 통해 코드를 가져와서 활용

  ```python
  # 일반적
  from my_package.math import tools
  print(tools.e)
  # 특정 함수나 어트리뷰트만 활용하고 싶을 때
  from my_package.math.tools import e
  print(e)
  # 해당하는 모듈 내의 모든 변수, 함수, 클래스를 가져옴
  # *(아스타리스크) 안쓰는거 추천 e, pi, my_max 등을 사용
  from my_package.math.tools import *  
  print(e)
  print(pi)
  # 지정하는 이름을 붙여서 가져옴
  from my_package.statistics.tools import standard_deviation as sd
  ```

  

## 01.27

### OOP_1

:  객체지향프로그래밍(Object Oriented Programming)

#### 1. 객체(Object)

- python에서 모든 것은 객체
- 모든 객체는 타입(type), 속성(attribute), 조작법(method)을 가짐
- 클래스에서 정의한 메서드를 수행 가능

**1.1 타입(Type)**

: 공통된 속성과 조작법을 가진 객체들의 분류

**1.2 인스턴스(Instance)**

: 특정 타입의 실제 데이터 예시

모든 객체는 특정 타입의 인스턴스

- ```python
  a = 10
  b = 20
  # a, b 는 객체이고 int 타입의 인스턴스
  ```

**1.3 속성(Attribute)**

: 객채의 상태/데이터

- ```python
  # complex
  complex_number = 6 + 8j
  complex_number.real  # 객체의 실수 속성
  complex_number.imag  # 객체의 허수 속성
  ```

**1.4 메서드(Method)**

: 특정 객체에 적용할 수 있는 행위

- ex) sort(), remove(), index() ...

:ballot_box_with_check: dir() : 객체가 가지고 있는 모든 속성과 메서드를 보여줌

#### 2. 객체 지향 프로그래밍(Object-Oriented Programming)

: Object가 중심(oriented)이 되는 프로그래밍

- OOP 장점
  - 코드의 직관성
  - 활용의 용이성
  - 변경의 유연성

#### 3.클래스(Class)

: 객체들의 분류를 정의할 때 쓰임, 공통된 속성과 메서드를 정의한 것

- 객체지향 프로그램의 기본적인 사용자 정의 데이터형

#### 4. 생성, 정의, 메서드

**4.1 클래스(Class) 생성**

- 클래스 내부에는 데이터와 함수를 정의할 수 있고 이때 데이터는 속성, 정의된 함순느 메서드 라고 부름

  ```python
  class Person:
      pass
  ```

:ballot_box_with_check: Check

- ```python
  print(type(Person))  ## <class 'type'>
  type(int)  ## type
  ```

**4.2 인스턴스(Instance) 생성**

- 클래스의 인스턴스는 클래스를 호출함으로써 생성

  ```python
  class Person:
      def __init__(self,name):
          self.name = name
  
  person_1 = Person('Mr.Lee')
print(person_1.name)  ## Mr.Lee
  # person1은 사용자가 정의한 Person이라는 데이터 타입의 인스턴스이다.
  kwanggyo = Person('kwanggyo')
  type(kwanggyo)  ## __main__.Person
  print(kwanggyo.name)  ## kwanggyo
  
  ```
  

**4.3 메서드(Method) 정의** 

: 특정 데이터 타입의 객체에 공통적으로 적용 가능한 행위

- self

  : 인스턴스 자신

  - Python 인스턴스 메서드에서는 호출 시 첫번째 인자로 인스턴스 자신이 전달되도록 설계

  - 보통 매개변수명으로 self를 첫번째로 설정(다른 이름 가능하지만 비추천!)

- 생성자(constructor) 메서드( ``def__init__(self)``)

  : 인스턴스 객체가 생성될 때 호출되는 함수

  - 생성자를 활용하여 인스턴스가 생성될 때 속성을 정의할 수 있음

- 소멸자(destructor) 메서드 (``def__del__(self)``)

  : 인스턴스 객체가 소멸되기 직전에 호출되는 함수

  ```python
  class Person:
      
      def __init__(self,name):
          self.name = name        
      
      def talk(self):
          print('hello')
          
      def walk(self, where='공원'):
          print(f'{where}을 걷는다.') # return 값으로도 줄 수 있음
          
  kwanggyo = Person('kwanggyo')
  kwanggyo.talk()  ## hello
  kwanggyo.walk()  ## 공원을 걷는다.
  kwanggyo.walk('학교')  ## 학교을 걷는다.
  ```

**4.4 속성(Attribute) 정의**

: 특정 데이터 타입의 객체들이 가지게 될 상태(데이터)

- 예시의 ``self.name = name`` 부분
- 호출할 때에는`` kwangggyo.talk()`` - 이런식으로

- dir() 함수를 통해 해당 객체가 활용 가능한 메서드를 확인할 수 있음

**4.5 매직매서드**

: 특별한 일을 하기 위해 만들어진 메서드

- 더블언더스코어(__)가 있음

  ```python
  __init__ : 인스턴스를 생성할 때 호출하는 메서드
      
  __del__ : 인스턴스를 삭제할 때 호출되는 메서드 
      
  __str__ : print할 때 원하는 출력이 나오게 하는 메서드
      
  __repr__ : 인스턴스를 호출했을 때 return 값을 지정하는 메서드
  ```





