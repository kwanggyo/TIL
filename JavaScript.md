# JavaScript

# `04.28`

## JavaScript

배워야하는 이유?

- 브라우저 화면을 `동적`으로 만들기 위해서 !
- 브라우저를 조작할 수 있는 유일한 언어

<br>

## 브라우저(browser)

- 웹 서버에서 이동하며 클라이언트와 서버간 양방향으로 통신하고 HTML 문서나 파일을 출력하는 GUI 기반의 소프트웨어
- 인터넷의 컨텐츠를 검색 및 열람하도록 한다.
- 웹 브라우저 라고도 한다.

<br>

### DOM

> - 문서(HTML) 조작

### BOM

> - 라우저의 객체를 조작
> - navigator, screen, location, frames, history, XHR

### JavaScript Core(ECMScript)

> - 프로그래밍 언어
> - Data Structure(Object, Array), Conditional Expression, Iteration

<br>

## DOM(Document Object Model)

HTML, XML 등과 같은 문서를 다루기 위한 언어 독립적인 문서 모델 인터페이스

문서를 구조화하고 구조화된 구성 요소를 하나의 객체로 취급하여 다루는 논리적 트리 모델 → 단계적으로 접근 가능

문서가 구조화되어 있으며 각 요소는 객체(object)로 취급

단순한 속성 접근, 메서드 활용 뿐만 아니라 프로그래밍 언어적 특성을 활용한 조작 가능

- 주요 객체
  - window : DOM을 표현하는 창, 가장 최상위 객체(작성 시 생략 가능)
  - document : 페이지 콘텐츠의 Entry Point 역할을 하며, <body>등과 같은 수많은 다른 요소들을 포함
  - navigator, location, history, screen

### DOM - 해석

> ##### Parsing(파싱)
>
> - 구문 분석, 해석
> - 브라우저가 문자열을 해석하여 DOM Tree로 만드는 과정

### DOM - 조작

> - Document는 문서 한 장(HTML)에 해당하고 이를 조작
> - DOM 조작 순서 → 기억 !
>   1. 선택(select)
>   2. 변경(manipulation)



# BOM

- Browser Object Model

- 자바스크립트가 브라우저와 소통하기 위한 모델

- 브라우저의 창이나 프레임을 추상화해서 프로그래밍적으로 제어할 수 있도록 제공하는 수당

  - 버튼, URL 입력창, 타이틀 바 등 브라우저 윈도우 및 웹 페이지의 일부분을 제어 가능

- window 객체는 모든 브라우저로부터 지원받으며 브라우저 window 자체를 지칭\

- 검사창에 아래 코드를 입력해보면 확인 가능

  ```javascript
  // 인쇄 창
  window.print()
  
  // 탭 창
  window.open()
  
  // 메세지 및 확인, 취소 버튼이 있는 대화상자 창
  window.confirm()
  
  // document도 브라우저 내에 종속되어 있기 때문에 window 전력 객체에 포함
  window.document
  ```

  

<hr>

# 주말에 추가 정리 예정



<br>

# `04.29`

# ECMAScript 6

- ECMA에서 제안하는 6번째 표준 명세(발표 연도에 따라 ECMAScript 20215라고도 한다.)

## ECMA

- 정보 통신에 대한 표준의 제정하는 비영리 표준화 기구

<br>

## 세이콜론(semicolon)

- 자바 스크립트는 세미콜론을 선택적으로 사용 가능하다 !
- 없을 경우 ASI(Automatic Semicolon Insertion)에 의해 자동으로 세미콜론이 삽입된다.

<br>

## 코딩 스타일 가이드

- 핵심은 

  ```
  합의된 원칙과 일관성
  ```

  - 절대적인 하나의 정답은 없으며, 상황에 맞게 원칙을 정하고 일관성 있게 사용하는 것이 중요하다.

- 코드의 품질에 직결되는 중요한 요소

  - 코드의 가독성, 유지보수 또는 팀원과의 커뮤니케이션 등 개발 과정 전체에 영향을 끼친다.

- 참고 스타일 가이드

  - https://github.com/airbnb/javascript
  - https://google.github.io/styleguide/jsguide.html
  - https://standardjs.com/#javascript-style-guide-linter-and-formatter

<br>

# 변수와 식별자

## 식별자(identifier)

- 식별자(identifier)는 변수를 구분할 수 있는 변수명을 말한다.
- 반드시 문자, 달러($), 밑줄(_)로 시작해야한다.
- 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작한다.
- 예약어 사용 불가능
  - ex) for, if, case 등

<br>

## 식별자 작성 스타일

1. 카멜 케이스(camelCase, lower-camel-case)
   - 변수, 객체, 함수에 사용
   - ex) getPropertyName, onClick
2. 파스칼 케이스(PascalCase, upper-camel-case)
   - 클래스, 생성자에 사용
   - ex) User
3. 대문자 스네이크 케이스(SNAKE_CASE)
   - 상수(constants)에 사용
     - 상수 : 개발자의 의도와 상관없이 변경될 가능성이 없는 값
   - ex) PI, API_KEY

<br>

## 변수 선언 키워드(let, const, var)

### let

> - 재할당 할 수 있는 변수 선언 시 사용
> - 변수 재선언 불가능
> - 불록 스코프(block scope)
>   - if, for, 함수 등의 `중괄호 내부`를 가리킨다.
>   - 블록 스코프를 가지는 변수는 `블록 바깥에서 접근 불가능`하다.

### const

> - 재할당 할 수 없는 변수 선언 시 사용
> - 변수 재선언 불가능
> - 블록 스코프

### var

> - 재선언 및 재할당 모두 가능하다.
> - ES6 이전에 변수를 선언할 때 사용되던 키워드
> - 호이스팅 되는 특성으로 인해 예기치 못한 문제 발생 가능
>   - 호이스팅(hoisting)
>     - 변수를 선언 이전에 참조할 수 있는 현상
>     - 변수 선언 이전의 위치에서 접근시 undefined를 반환
>     - 예시
>   - ES6 이후부터는 var 대신 const와 let 사용을 권장한다.
> - 함수 스코프(function scope)
>   - `함수의 중괄호 내부`를 가리킨다.
>   - 함수 스코프를 가지는 변수는 `함수 바깥에서 접근 불가능` 하다.

<br>

## 선언, 할당, 초기화

### 선언(Declartation)

> - 변수를 생성하는 행위 또는 시점

### 할당(Assignment)

> - 선언된 변수에 값을 저장하는 행위 또는 시점

### 초기화(Initialization)

> - 선언된 변수에 처음으로 값을 저장하는 행위 또는 시점

<br>

