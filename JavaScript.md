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

## History of JavaScript

### 핵심 인물

> 1. 팀 버너스리(Sir Tim Berners-Lee)
>    - WWW, URL, HTTP, HTML 최초 설계자
>    - 웹의 아버지
> 2. 브랜던 아이크(Brendan Eich)
>    - JavaScript 최초 설계자
>    - 모질라 재단 공동 설립자
>    - 코드네임 피닉스 프로젝트 진행
>      - 파이어폭스의 전신

### 간단 정리

> - 브라우저 전쟁 → 파편화 & 표준화 투쟁
>
> - 구글 크롬 승리 → 압도적인 속도와 웹 표준을 가장 잘 지켰음!
>
> - 브라우저 전쟁의 여파
>
>   - Cross Browsing Issue
>   - 표준화(통합)을 위한 노력
>   - Vanilla JavaScript
>
> - 공식명칭은 ES2015지만 ES6라고 부름
>
> - ES6+는 ES2015 이후를 말함
>
> - 2009 → 2015 에서 가장 큰 대격변이 일어남(ES5 → ES6)
>
> - +
>
>   ```
>   두번의 브라우저 전쟁
>   
>   브라우저 전쟁으로 파편화가 되었고 
>   
>   그 여파로 크로스 브라우징 이슈(cross Browsing Issue) 발생
>   
>   파편화 투쟁 그 중심에는 모질라와 크롬이 있었다.
>   
>   크로스 브라우징
>   
>   - W3C에서 채택된 표준 웹 기술을 채택해 서로 다른 브라우저에서 다르게 구현되는 기술을 비슷하게 만들며 웹 페이지를 제작하는 방법론(동등성)
>   - 브라우저마다 렌더링에 사용하는 엔진이 다르기 때문에
>   
>   Vanilla JavaScript, jQuery 등 많은 라이브러리 등장
>   
>   - 순수한 언어 그 자체 : Vanila, 순수한 자바스크립트 그 자체로 사용
>   ```

<br>

## DOM vs BOM

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

<br>

## BOM

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


<br>

## DOM 선택 - 선택 관련 메서드

- DOM 조작은 선택 후 조작 !!
- 연습 사이트 : https://flukeout.github.io/
- 선택자를 통해 태그를 설정하고 우클릭 copy selector로 원하는 부분의 태그를 알 수도 있다.

### Document.querySelector()

> - () 안에 인자가 들어갈 건데 제공한 선택자(div)와 일치하는 `element 하나 선택`
> - 제공한 CSS selector를 만족하는 `첫번째 element 객체`를 반환(없다면 null)

### Document.querySelectorAll()

> - 제공한 선택자와 일치하는 `여러 element를 선택`
> - 매칭할 하나 이상의 셀렉터를 포함하는 유효한 CSS selector를 인자(문자열)로 받음
> - 지정된 셀렉터에 일치하는 NodeList를 반환
>
> - 
>
> - getElementById(), getElementByTagName(), getElementByClassName()은 각각에 해당하는 것만 사용 가능 → querySelector(), querySelectorAll()을 사용하는 이유
> - id, class 그리고 tag 선택자 등을 모두 사용하기 때문에 더 구체적이고 유연하게 선택 가능

<br>

## DOM 선택 - 메서드별 반환 타입

### 단일 element

> - getElementById()
> - querySelector()

### HTMLCollection(live collection)

> - getElementByTagName()
> - getElementByClassName()

### NodeList(static collection)

> - querySelectorAll()

### HTMLCollection & NodeList

> - 쿼리딕트, 오더딕트 → 배열과 유사하게 사용 : 유사 배열
> - 둘 다 배열과 같이 각 항목을 접근하기 위한 인덱스를 제공(유사 배열)
> - 둘 다 `Live Collection`으로 DOM의 변경사항을 실시간으로 반영하지만, querySelectorAll()의 의해 반환되는 NodeList는 Static Collection
>
> #### HTML Collection
>
> - name, id, 인덱스 속성으로 각 항목들에 접근 가능
>
> #### NodeList
>
> - 인덱스 번호로만 각 항목들에 접근 가능
> - 단, HTMLCollection과 달리 배열에서 사용하는 for each 함수 및 다양한 메서드 사용가능

### Collection

> #### Live Collection
>
> - 문서가 바뀔 때 실시간으로 업데이트
> - DOM의 변경사항을 실시간으로 collection에 반영
> - ex) HTMLCollection, NodeList
>
> #### Static Collection
>
> - DOM이 변경되어도 collection 내용에는 영향을 주지 않음
> - querySelectorAll()의 반환 NodeList만 static

<br>

## DOM - 변경 관련 메서드

### Document.createElement()

> - 주어진 태그명을 사용해 HTML 요소를 만들어 반환

### ParentNode.append()

> - 특정 부모 노드의 자식 노드 리스트 중 마지막 자식 다음에 Node객체나 DOMString을 삽입(반환값 없음)
> - 여러개의 Node 객체, DOMString을 추가 할 수 있음

### Node.appendChild()

> - 한 노드를 특정 부모 노드의 자식 노드 리스트 중 마지막 자식으로 삽입(Node만 추가 가능)
> - 만약 주어진 노드가 이미 문서에 존재하는 다른 노드를 참조한다면 새로운 위치로 이동

### ChildNode.remove()

> - 이를 포함하는 트리로부터 특정 객체를 제거

### Node.removeChild()

> - DOM에서 자식 노드를 제거하고 제거 된 노드를 반환
> - Node는 인자로 들어가는 자식 노드의 부모 노드

<br>

## DOM 변경 - 변경 관련 속성(property) - 괄호 없음

### Node.innerText

> - 노드와 그 자손의 텍스트 컨텐츠(DOMString : 문자열로 생각)를 표현(해당 요소 내부의 raw text) (사람이 읽을 수 있는 요소만 남김)
> - 즉, 줄 바꿈을 인식하고 숨겨진 내용을 무시하는 등 최종적으로 스타일링이 적용된 모습으로 표현
> - `<h1>Hi</h1>` 에서 Hi를 의미

### Element.innerHTML

> - 요소(element) 내에 포함된 HTML 마크업을 반환
> - XSS 공격에 취약점이 있으므로 사용시 주의

### XSS

> - 공격자가 웹 사이트 클라이언트 측 코드에 악성 스크립트를 삽입해 공격하는 방법
> - 이 코드의 실행은 피해자가 하며 공격자가 엑세스 제어를 우회하고 사용자를 가장할 수 있도록 함(csrf 공격과 유사)
> - ex)
>   - 게시판이나 메일 등 악성 자바스크립트 코드를 삽입해 개발자가 고려하지 않은 기능이나 공격이 작동
>   - 공격에 성공하면 사용자의 쿠키나 세션 등 민감한 정보를 탈취

<br>

## 변경 관련 메서드

### Element.setAttribute(name, value)

> - 지정된 요소의 값을 설정
> - 속성이 이미 존재하면 값을 업데이트, 그렇지 않으면 지정된 이름과 값으로 새 속성 추가
> - <h1_____  > ~~~ </h1> : _____이 부분을 넣어준다.

### Element.getAttribute()

> - 해당 요소의 지정된 값(문자열)을 반환
> - 인자는 값을 얻고자 하는 속성의 이름

<br>

# Event

- 네트워크 활동 혹은 사용자와의 상호작용 같은 사건(특정한 사건)의 발생을 알리기 위한 객체
- 이벤트는 마우스를 클릭하거나 키보드를 누르는 등 사용자 행동에 의해 발생할 수도 있고, 특정 메서드를 호출하여 프로그래밍적으로도 만들어낼 수 있음
- ex) ~ 하면 ... 한다 → ~ : Event
  - 클릭하면 경고 창을 띄운다.
  - 이벤트가 발생하면 할 일을 등록한다.
- 이벤트 처리기(Event-handlers)
  - EventTarget.addEventListener()를 통해 다양한 요소에서 이벤트를 붙일 수 있다.
  - removeEventListener()를 통해 이벤트를 제거 가능

<br>

## Event 기반 인터페이스

- Animation, ClipborardEvent, DragEvent 등

- 그 중에서도 

  ```
  UIEvent
  ```

  - 간단한 사용자 인터페이스 이벤트
  - Event(최상위 객체)의 상속을 받음
  - MouseEvent, KeyboardEvent, InputEvent, FocusEvent 등의 부모 객체 역할을 함

- https://developer.mozilla.org/ko/docs/Web/Events : 이벤트 이름

<br>

## Event handler

- 특정 이벤트가 발생하면 할 일을 등록한다.
- EventTarget.addEventListener()
- 지정한 이벤트가 대상에 전달될 때마다 호출할 함수를 설정
- 이벤트를 지원하는 모든 객체(Element, Document, Window 등)를 대상으로 지정 가능
- target.addEventListener(type, listener[, options])
  - type : 반응 할 이벤트 유형(대소문자 구분 문자열)
  - listener : 지정된 타입의 이벤트가 발생했을 때 알림을 받는 객체
  - EventListener 인터페이스 혹은 JS function 객체(콜백 함수)여야 한다.

<br>

## addEventListner

- 특정 이벤트가 발생하면, 할 일을 등록하자
- EventTarget.addEventListener(type, listener)
  - ex) EventTarget: 버튼, type: 클릭, listener: 새로운 그림을 보여준다.
  - listener에는 앞에서 발생한 event가 기본 인자로 넘어온다.
- 어디선가 함수를 실행하게 되면 반드시 브라우저는 event 객체를 넣어준다. 쓰지 않는다면 function 후에 (event)를 안넣어줘도 됨 → django에서는 안쓰더라도 url에 pk가 있으면 넣어줬어야 함

### preventDefault()

> - 현재 이벤트의 기본 동작을 중단
> - 태그의 기본 동작(a 태그는 클릭시 페이지 이동, form 태그는 폼 데이터를 전송)
> - 이벤트의 전파를 막지 않고 이벤트의 기본동작만 중단시킴
> - ex) a태그를 클릭했다는 이벤트는 남기고 페이지 이동은 x(기본 동작을 막음)
> - `발생하는 이벤트는 사용할 수 있다!

<br>

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

# 데이터 타입

## 데이터 타입 종류

- 자바 스크립트의 모든 값은 특정한 데이터 타입을 가진다.
- 크게 원시 타입과 참조타입으로 분류된다.

## 원시 타입(Primitive type)

- 객체가 아닌 기본 타입들을 말한다.
- 변수에 해당 타입의 값이 담긴다.
- 다른 변수에 복사할 때 실제 값이 복사된다.

<br>

### 1. 숫자(NUmber) 타입

> - 정수, 실수 구분 없는 하나의 숫자 타입
> - 부동소수점 형식을 따름
> - NaN(Not-A-Number)
>   - 계산 불가능한 경우 반환 되는  값
>   - NaN : 숫자가 아니다
>   - 문자열을 숫자로 나눔 → 에러를 발생시키지 않고 NaN으로 나타냄
>     - ex) 'Angel' / 1004 → NaN

### 2. 문자열(String) 타입

> - 텍스트 데이터를 나타내는 타입
> - 16비트 유니코드 문자의 집합
> - 작은 따옴표, 큰 따옴표 모두 가능
> - 템플릿 리터럴(Template Literal)
>   - ES6부터 지원
>   - 따옴표 대신 backtick(`)으로 표현
>   - ${expression} 형태로 표현식 삽입 가능

### 3. undefined

> - 변수의 값이 없음을 나타내는 데이터 타입
> - 변수 선언 이후 직접 값을 할당하지 않으면 자동으로 undefined가 할당된다.

### 4. null

> - 변수의 값이 없음을 의도적으로 표현할 때 사용하는 데이터 타입
> - (참고) null 타입과 typeof 연산자
>   - typeof 연산자 : 자료형 평가를 위한 연산자
>   - null 타입은 ECMA 정의에 따라 원시 타입에 속하지만 typeof 연산자의 결과는 객체로 표현된다.

### #. undefined와 null 비교

> - 공통점 : 빈 값을 표현하기 위한 데이터타입
> - 차이점
>   - undefined : 변수 선언 시 아무 값도 할당하지 않으면 자바스크립트가 자동으로 할당
>     - typeof 연산자의  결과는 undefined
>   - null : 개발자가 의도적으로 필요에 의해 할당
>     - typeof 연산자의 결과는 object

### 5. 불리언(Boolean) 타입

> - 논리적 참 또는 거짓을 나타내는 타입
>
> - true 또는 false로 표현
>
> - 조건문 또는 반복문에서 유용하게 사용
>
>   - 조건문 또는 반복문에서 불리언이 아닌 데이터 타입은 자동 형변환 규칙에 따라 true 또는 false로 변환됨
>
> - 자동 형변환 정리
>
>   | 데이터 타입 |    거짓    |        참        |
>   | :---------: | :--------: | :--------------: |
>   |  Undefined  | 항상 거짓  |        X         |
>   |    Null     | 항상 거짓  |        X         |
>   |   Number    | 0, -0, NaN | 나머지 모든 경우 |
>   |   String    | 빈 문자열  | 나머지 모든 경우 |
>   |   Object    |     X      |     항상 참      |

<br>

## 참조 타입(Reference type)

- 객체 타입의 자료형들을 말한다.
- 변수에 해당 객체의 참조 값이 담김
- 다른 변수에 복사할 때 참조 값이 복사됨
- 함수(Functions), 배열(Arrays), 객체(Objects)

<br>

# 연산자

## 연산자 종류

### 1. 할당 연산자

> - 오른쪽에 있는 피연산자의 평가 결과를 왼쪽 피연사에 할당하는 연산자
> - 다양한 연산에 대한 단축 연산 지원

### 2. 비교 연산자

> - 피연자들(숫자, 문자, Boolean 등)을 비교하고 비교의 결과값을 불리언으로 반환하는 연산자
> - 문자열은 유니코드 값을 사용하며 표준 사전순서를 기반으로 비교
>   - 알파벳 오름차순으로 우선순위를 지님
>   - 소문자가 대문자보다 우선순위를 지님

### 3. 동등 비교 연산자(==)

> - 두 피연산자가 같은 값으로 평가되는지 비교 후 불리언 값을 반환
> - 비교할 때 암묵적 타입 변환을 통해 타입을 일치시킨 후 같은 값인지 비교
> - 두 피연산자가 모두 객체일 경우 메모리의 같은 객체를 바라보는지 판별
> - 예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음

### 4. 일치 비교 연산자(===)

> - 두 피연산자가 같은 값으로 평가되는지 비교 후 불리언 값을 반환
> - 엄격한 비교가 이뤄지며 암묵적 타입 변환이 발생하지 않음
>   - 엄격한 비교 : 두 비교 대상의 타입과 값 모두 같은지 비교하는 방식
> - 두 피연산자가 모두 객체일 경우 메모리의 같은 객체를 바라보는지 판별

### 5. 논리 연산자

> - 세 가지 논리 연산자로 구성
>   - and 연산은 && 연산자를 이용
>   - or 연산은 || 연산자를 이용
>   - not 연산은 ! 연산자를 이용
> - 단축 평가 지원
>   - 파이썬과 같다.
>   - ex) false && true → false
>   - ex) true || false → true

### 6. 삼항 연산자(Ternary Operator)

> - 세 개의 피연산자를 사용하여 조건에 따라 값을 반환하는 연산자
>
> - 가장 왼쪽의 조건식이 참이면 콜론(:) 앞의 값을 사용하고 그렇지 않으면 콜론(:) 뒤의 값을 사용
>
> - 삼항 연산자의 결과는 변수에 할당 가능
>
> - 한 줄에 표기하는 것을 권장
>
> - 파이썬의 조건 표현식과 비슷
>
>   ```python
>   # 파이썬 조건표현식
>     
>   x = 10
>   hello = 'world' if 4 > x else 'hello'
>   ```

<br>

# 조건문

## 조건문의 종류와 특징

- if statement
  - 조건 표현식의 결과값을 Boolean 타입으로 변환 후 참/거짓을 판단
- switch statement
  - 조건 표현식의 결과값이 어느 값(case)에 해당하는지 판별
  - 주로 특정 변수의 값에 따라 조건을 분기할 때 활용한다.
  - 조건이 많아질 경우 if문보다 가독성이 나을 수 있다.

### if statement

> - If, else if, else
>
>   - 조건은 소괄호(condition) 안에 작성
>
>   - 실행할 코드는 중괄호{} 안에 작성
>
>   - 블록 스코프 생성
>
>     ```python
>     if (li) {
>     	console.log('hello')
>     }
>     -> hello가 출력됨!
>     -> li가 객체이기 때문에 참으로 판별
>     ```

### switch statement

> - switch
>   - 표현식(expression)의 결과값을 이용한 조건문
>   - 표현식의 결과값과 case문의 오른쪽 값을 비교
>   - break 및 default문은 선택적으로 사용 가능
>   - break문이 없는 경우 break문을 만나거나 default문을 실행할 때까지 다음 조건문 실행
>   - 블록 스코프 생성

<br>

# 반복문

## 반복문의 종류와 특징

- while
- for
- for in
  - 주로 객체의 속성들을 순회할 때 사용
  - 배열도 순회 가능하지만 인덱스 순으로 순회한다는 보장이 없으므로 권장하지 않는다.
- for of
  - `반복 가능한(iterable) 객체`를 순회하며 값을 꺼낼 때 사용
  - 반복 가능한 객체의 종류 : Array, Map, Set, String 등

### while

> - 조건문이 참(true)인 동안 반복 시행
> - 조건은 소괄호(condition) 안에 작성
> - 실행할 코드는 중괄호{} 안에 작성
> - 블록 스코프 생성

### for

> - 세미콜론(;)으로 구분되는 세 부분 으로 구성
> - initialization
>   - 최초 반복문 진입시 1회만 실행되는 부분
> - condition
>   - 매 반복 시행 전 평가되는 부분
> - expression
>   - 매 반복 시행 이후 평가되는 부분
> - 블록 스코프 생성

### for in

> - `객체(object)의 속성들을 순회`할 때 사용
> - 배열도 순회 가능하지만 권장하지 않음
> - 실행할 코드는 중괄호 안에 작성
> - 블록 스코프 생성

### for of

> - `반복 가능한(iterable) 객체를 순회`하며 값을 꺼낼 때 사용
> - 실행할 코드는 중괄호 안에 작성
> - 블록 스코프 생성

<br>

# 함수

- 참조 타입 중 하나로써 function 타입에 속한다.
- 정의 방법
  - 함수 선언식(function declaration)
  - 함수 표현식(function expression)
- `일급 객체`에 해당한다. → 면접에도 나올 수 있음 
  - 변수에 할당 가능
  - 함수의 매개변수로 전달 가능
  - 함수의 반환 값으로 사용 가능

<br>

## 함수의 선언식

- 함수의 이름과 함께 정의하는 방식
- 구성
  - 함수의 이름(name)
  - 매개변수(args)
  - 몸통(중괄호 내부)

<br>

## 함수 표현식

- 함수의 이름을 생략하고 익명 함수로 정의 가능
  - 익명 함수 : 이름이 없는 함수로 함수 표현식에서만 가능
  - 표현식 : 어떤 하나의 값으로 결정되는 코드의 단위
- 구성
  - 함수의 이름(name) - 생략 가능
  - 매개변수(args)
  - 몸통(중괄호 내부)

<br>

## 기본 인자(default arguments)

- = 문자 뒤 기본 인자 선언 가능

<br>

## 호이스팅(hoisting) - 함수 선언식

- 함수 선언식으로 선언한 함수는 var로 정의한 변수처럼 hoisting 발생
- 함수 호출 이후에 선언 해도 동작 → 이렇게 사용 하지 않는다.

<br>

## 호이스팅(hoisting) - 함수 표현식

- 함수 표현식으로 선언한 함수는 함수 정의 전에 호출 시 에러 발생
- 함수 표현식으로 정의된 함수는 변수로 평가되어 변수의 scope 규칙을 따름
- 함수 표현식을 var 키워드로 작성한 경우, 변수가 선언 전 undefined로 초기화 되어 다른 에러가 발생

<br>

## 화살표 함수(Arrow Function)

- 함수를 비교적 간결하게 정의할 수 있는 문법
- function 키워드 생략 가능
- 함수의 매개변수가 단 하나 뿐이라면, ‘( )’ 도 생략 가능
- 함수 몸통이 표현식 하나라면 ‘{ }’과 return도 생략 가능
- 간결해서 사용, 깊게 들어가면 function과 다른점이 있어서 arrow function을 사용해야할 때가 있음

<br>

# 배열

## 배열의 정의와 특징

- 키와 속성들을 담고 있는 참조 타입의 객체(object)
- 순서를 보장하는 특징이 있음
- 주로 대괄호를 이용하여 생성하고, 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
- 배열의 길이는 array.length 형태로 접근 가능
  - 마지막 원소는 array.length -1로 접근
- 관련 메서드 참고 사이트

<br>

## 주요  기본 메서드

### reverse

> - array.reverse()
>   - 원본 배열의 요소들의 순서를 반대로 정렬

### push & pop

> - array.push()
>   - 배열의 가장 뒤에 요소 추가
>   - 파이썬의 appen
> - array.pop()
>   - 배열의 마지막 요소 제거

### unshift & shift

> - array.unshift()
>   - 배열의 가장 앞에 요소 추가
> - array.shift()
>   - 배열의 첫번째 요소 제거

### includes

> - array.includes(value)
>   - 배열에 특정 값이 존재하는지 판별 후 참 또는 거짓 반환
>   - 파이썬의 in

### indexOf

> - array.indexOf(value)
>   - 배열에 특정 값이 존재하는지 확인 후 가장 첫번째로 찾은 요소의 인덱스 반환
>   - 만약 해당 값이 없을 경우 -1 반환

### join

> - array.join([separator])
>   - 배열의 모든 요소를 연결하여 반환
>   - seperator(구분자)는 선택적으로 지정 가능하며, 생략 시 쉼표를 기본 값으로 사용
>   - default : ,

<br>

## 주요 심화 메서드

- 배열을 순회하며 특정 로직을 수행하는 메서드

- 메서드 호출 시 인자로 callback 함수를 받는다.

  - callback 함수 : 어떤 함수의 내부에서 실행될 목적으로 인자로 넘겨받는 함수

    ex) django의 views.index

### forEach

> - array.forEach(callback(element[, index[, array]]))
>   - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
>   - 콜백 함수는 3가지 매개변수로 구성
>     - element: 배열의 요소
>     - index: 배열 요소의 인덱스
>     - array: 배열 자체
>   - `반환 값(return)이 없는 메서드`

### map

> - array.map(callback(element[, index[, array]]))
>   - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
>   - `콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환`
>   - 기존 배열 전체를 다른 형태로 바꿀 때 유용

### filter

> - array.filter(callback(element[, index[, array]]))
>
>   - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
>   - `콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열을 반환`
>   - 기존 배열의 요소들을 필터링할 때 유용
>
>   ```python
>   const arr = [1, 2, 3, 4, 5]
>   arr.filter((number) => {
>       return number%2 === 1
>   })
>   // [1, 3, 5]
>     
>   arr.filter((number) => {
>       return number%2 === 0
>   })
>   // [2, 4]
>   ```
>
>   

### reduce

> - array.reduce(callback(acc, element, [index[, array]])[, initialValue])
>   - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
>   - `콜백 함수의 반환 값들을 하나의 값(acc)에 누적 후 반환`
>   - 많이 사용된다.
>   - reduce 메서드의 주요 매개변수
>     - acc: 이전 callback 함수의 반환 값이 누적되는 변수
>     - initialValue: 최초 callback 함수 호출 시 acc에 할당되는 값으로, 선택적으로 설정 가능하며 직접 제공하지 않으면 배열의 첫번째 값 사용
>     - 빈 배열의 경우 initialValue를 제공하지 않으면 에러 발생

### find

> - array.find(callback(element[, index[, array]]))
>   - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
>   - `콜백 함수의 반환 값이 참이면 해당 요소를 반환`
>   - 찾는 값이 배열에 없으면 undefined 반환

### some

> - array.some(callback(element[, index[, array]]))
>   - `배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 참을 반환`
>   - 모든 요소가 통과하지 못하면 거짓 반환
>   - 빈 배열은 항상 거짓 반환

### every

> - array.every(callback(element[, index[, array]]))
>   - `배열의 모든 요소가 주어진 판별 함수를 통과하면 참을 반환`
>   - 모든 요소가 통과하지 못하면 거짓 반환
>   - 빈 배열은 항상 참 반환

<br>

# 객체(Objects)

## 객체의 정의와 특징

- 객체는 속성(property)의 집합이며 중괄호 내부에 key와 value의 쌍으로 표현
- 객체 안에 함수가 들어가 있으면 메서드
- key는 문자열 타입만 가능
  - key 이름에 띄어쓰기 등의 구분자가 있을 경우 따옴표로 묶어서 표현
- value는 모든 타입 가능
  - 객체 요소 접근은 점 또는 대괄호로 가능
    - key 이름에 띄어쓰기 같은 구분자가 있을 경우 대괄호 접근만 가능

<br>

## 객체 관련 ES6 문법

### 속성명 축약(shorthand)

> - 객체를 정의할 때 key와 할당하는 변수의 이름이 같으면 예시와 같이 축약 가능

### 메서드명 축약(shorthand)

> - 메서드 선언 시 function 키워드 생략 가능

### 계산된 속성(computed property name)

> - 객체를 정의할 때 key의 이름을 표현식을 이용하여 동적으로 생성 가능

### 구조 분해 할당(destructing assignment)

> - 배열 또는 객체를 분해하여 속성을 변수에 쉽게 할당할 수 있는 문법

<br>

## JSON(JavaScript Object Notation)

- key-value쌍의 형태로 데이터를 표기하는 언어 독립적 표준 포맷
- 자바스크립트의 객체와 유사하게 생겼으나 실제로는 문자열 타입
- 자바스크립트에서는 JSON을 조작하기 위한 두 가지 내장 메서드 제공
  - JSON.parse() : JSON → 자바스크립트 객체
  - JSON.stringify() : 자바스크립트 객체 → JSON

<br>

<br>

# 05.03

# AJAX

- Asynchronous Javascript And XML (비동기식 js와 xml)
- 서버와 통신하기 위해 XMLHttpRequest 객체를 활용
  - XMLHttpRequest는 동기식과 비동기식 통신을 모두 지원
- 페이지 전체를 reload를 하지 않고서도 수행되는 `비동기성`
  - 사용자의 event가 있으면 `전체 페이지가 아닌 일부분만을 업데이트`
- AJAX의 X가 XML을 의미하긴 하지만, 요즘은 더 가벼운 용량과 JavaScript의 일부라는 장점 때문에 `JSON`을 더 많이 사용
- 특정 기술이 아닌 기존의 여러 기술을 사용하는 새로운 접근법을 설명하는 용어로, 기존 기술을 잘 활용할 수 있는 방식으로 구성 및 재조합한 새로운 접근법이다.
- ex)
  - 메일의 전송 버튼을 눌러 놓고 다른 페이지로 넘어가도 메일은 알아서 전송 처리됨(Gmail)
  - 스크롤하는 행위 하나하나가 모두 요청이지만 페이지는 갱신되지 않음(Google Maps)

<br>

# XMLHttpRrequest object

- 서버와 상호작용하기 위해 사용되며, 전체 페이지의 새로고침 없이 URL로부터 데이터를 받아올 수 있음
- 사용자가 하는 것을 방해하지 않으면서 페이지의 일부를 업데이트할 수 있도록 해줌
- 주로 AJAX 프로그래밍에 사용
- XML뿐만 아니라 `모든 종류의 데이터를 받아오는데 사용 가능`
- 생성자
  - XMLHttpRequest() 사용
- XMLHttpRequest는 사용방법이 복잡하기 때문에 axios라는 라이브러리를 가져와서 사용함
- Vue는 XMLHttpRequest대신 axios를 사용

<br>

# 동기(Synchronous)와 비동기(Asynchronous)

### 동기식

> - 순차적, 직렬적 태스크 수행
> - 요청을 보낸 후 응답을 받아야만 다음 동작이 이루어짐(blocking)

### 비동기식

> - 병력적 태스크 수행
>
> - 요청을 보낸 후 응답을 기다리지 않고 다음 동작이 이루어짐(non-blocking)
>
>   → 요청을 보내놓고 다음 태스크로 진행

### 차이점

> - 비동기는 진행 중에 다른 것도 같이 진행 가능, 동기는 진행 중인 일이 끝나야 다음 일 진행 가능하다.(기다림의 여부)

<br>

## 비동기를 사용하는 이유?

```
Human-centered design with UX : 사용자 경험을 갖춘 인간 중심 설계
```

- 사용자의 경험 때문에 사용 !

- 예를 들어 데이터를 구동하고 실행되는 앱이 있으며 이 데이터의 크기가 굉장히 크다고 가정한다.

  동기식 코드라면 데이터를 모두 로드 한 뒤에야 앱이 실행되기 때문에 로드 되는 동안 우리는 앱을 사용할 수 없는 상태로 얼마나 걸릴지 모르는 로딩 시간을 기다려야 한다.

  즉, 앱이 멈춘 것처럼 보일 수 있고 동기식 요청은 코드 실행을 차단하여 화면이 멈추고 응답하지 않는 사용자 경험을 만든다.

  이러한 사용자 경험은 다시 이용하는데 영향을 끼칠 수 있고 많은 웹 API 기능은 비동기 코드들 사용하여 실행 된다.

- ex) axios.get(로또).then(() ⇒ {}) → 시간이 얼마나 걸릴 모르는 일임 → 사용자가 내 서버를 떠나가지 않게끔 할 일을 이어서 함

<br>

## JS → Single Threaded

- 컴퓨터가 여러 개의 CPU를 가지고 있어도 main thread라 불리는 단일 스레드에서만 작업 수행

  → 이벤트를 처리하는 Call Stack이 하나의 언어라는 의미

- 이 문제를 해결하기 위해 즉시 처리하지 못하는 이벤트들을 다른 곳(`Web API`)으로 보내서 처리하도록 하고, 처리된 이벤트 들은 순서대로 대기실(`Task queue`)에 줄을 세워 놓고 Call Stack이 비면 담당자(`Event Loop`)가 대기 줄에서 가장 오래된(FIFO) 이벤트를 Call Stack으로 보낸다.

### Threads

> - 프로그램이 작업을 완료하는데 사용할 수 있는 단일 프로세스
> - 각 thread는 한번에 하나의 작업만 수행할 수 있음
>   - 다음 작업을 시작하려면 반드시 앞의 작업이 완료되어야 함
>   - 컴퓨터 CPU는 여러 코어를 가지고 있기 때문에 한번에 여러가지 일을 처리할 수 있다.

<br>

## Concurrency model

- Event loop를 기반으로 하는 동시성 모델
- 순서를 보장할 수 없음

### Call Stack

> - 메인 일처리
> - 요청이 들어올 때마다 해당 요청을 순차적으로 처리하는 Stack(LIFO) 형태의 자료 구조

### Web API (Browser API)

> - 다른 곳에서 일처리
> - JavaScript 엔진이 아닌 브라우저 영역에서 제공하는 API
>   - Thread를 도와준다.
> - setTimeout(), DOM events, AJAX로 데이터를 가져오는 시간이 소요되는 일들을 처리

### Task Queue (Event Queue, Message Queue)

> - 다른 곳에서 일처리가 끝난 것들이 들어있는 대기실
> - 콜백 함수가 대기하는 Queue(FIFO) 형태의 자료 구조
> - main thread가 끝난 후 실행되어 후속 JavaScript 코드가 차단되는 것을 방지

### Event Loop

> - 일이 남아있는지 체크
> - Call Stack이 비어 있는지 여부를 확인하고 비어 있는 경우 Task Queue에서 실행 대기중인 콜백인 있는지 확인, 대기준인 콜백이 있다면 가장 앞의 콜백을 Call Stack으로 push한다.

<br>

## Zero delays

- 실제로 0ms 후에 콜백이 시작된다는 의미가 아님 !
- 실행은 Task Queue에 대기중인 작업 수에 따라 다르다.
- delay는 JS가 `요청을 처리하는데 필요한 최소 시간`이기 때문(`보장된 시간이 아니다`)
- 기본적으로 setTimeout()은 setTimeout에 대한 특정 시간 제한을 지정 했더라도 대기중인 메세지의 모든 코드가 완료 될 때까지 대기해야한다.

<br>

## 순차적으로 비동기를 처리하는 방식

- Web API로 들어오는 순서는 중요하지 않고 어떤 이벤트가 먼저 처리 되느냐가 중요(실행 순서 불명확)
- 콜백큐에 들어오는 순서대로 처리하는 것이 순차적인 비동기처리
- 해결하기 위한 2가지 방식

1. Async callbacks
   - 백그라운드에서 실행을 시작할 함수를 호출할 때 인자로 지정된 함수
   - ex) addEventListener()의 두번째 인자
2. promise-style
   - Modern Web APIs에서의 새로운 코드 스타일
   - XMLHttpRequest보다 조금 더 현대적인 버전

<br>

## Callback Function

- 다른 함수에 인자로 전달된 함수
- 외부 함수 내에서 호출되어 일종의 루틴 또는 작업을 완료함
- `동기식, 비 동기식 모두 사용됨`
  - 무조건 비동기인 것이 아님 !!
- 비동기 작업이 완료된 후 코드 실행을 계속하는데 사용되는 경우 비동기 콜백이라고 한다.
- 비동기로직에서는 명시적인 호출이 아니기 때문에 콜백 함수 필수
  - 명시적인 호출 ex) sum()

### Async callbacks

> - 백그라운드에서 코드 실행을 시작할 함수를 호출할 때 인자로 지정된 함수
> - 백그라운드 코드 실행이 끝나면 콜백 함수를 호출하여 작업이 완료되었음을 알리거나 다음 작업을 실행하게 할 수 있다.
> - 특정한 순차적인 것이 있다면 백그라운드에서 수행
>   - ex) eventListener

### JS의 함수 → 일급 객체(First-class object)

> - 다른 객체들에 적용 가능한 연산을 모두 지원하는 객체(함수)
> - 일급 객체의 조건
>   1. 인자로 넘길 수 있어야 한다.
>   2. 함수의 반환 값으로 사용할 수 있어야 한다.
>   3. 변수에 할당할 수 있어야 한다.

### Callback을 사용하는 이유

> - 콜백 함수는 명시적인 호출이 아닌 특정 routine 혹은 action에 의해 호출되는 함수이다.
> - Callback Function  매커니즘이 있기 때문에 Django의 "요청이 들어오면", event의 "특정 이벤트가 발생하면" 이라는 조건 하에서 함수를 호출 가능
> - 비동기 로직을 수행할 때 콜백 함수는 필수
>   - 명시적인 호출이 아닌 `특정 시점에 알아서 호출되도록 만들어야 하기 때문`이며 기다려주지 않고 언젠가 처리해야 하는 일은 콜백 함수를 활용

### Callback Hell

> - 여러 개의 비동기 작업을 할 때 순차적인 연쇄 비동기 작업을 처리하기 위해 콜백 함수를 계속적으로 호출하는 패턴이 반복되는 상황
> - 디버깅이 힘들고 코드 가독성이 떨어진다.

### Callback Hell 해결방법

> 1. Keep your code shallow(코드의 깊이를 얕게 유지)
> 2. Modularize(모듈화)
> 3. Handle every single error(모든 단일 오류 처리)
> 4. `Promise way (Promise 방식 사용)`

<br>

## Promise

- 비동기 작업의 최종 완료 또는 실패를 나타내는 객체
  - 미래의 완료 또는 실패와 그 결과 값을 나타낸다.
  - 미래의 어떤 상황에 대한 약속
- 성공(이행) → .then()
- 실패(거절) → .catch()

### Promise 기본 구조

> - 두개의 콜백 함수를 인자로 받음
> - Promise가 성공했을 때 → resolve()
> - Promise가 실패했을 때 → reject()

### .then(callback)

> - 이전 작업(promise)이 성공했을 때 수행할 작업을 나타내는 콜백 함수
> - 각 콜백 함수는 이전 작업의 성공 결과를 인자로 전달 받는다.
> - 성공했을 때의 코드를 콜백 함수 안에 작성
> - 각각의 .then 블록은 서로 다른 promise를 반환하기 때문에 .then을 여러개 사용(`chaining`)하여 연쇄적인 작업을 수행할 수 있다. → 여러 비동기 작업을 차례대로 수행할 수 있다 !
> - .catch도 promise를 반환하기 때문에 chaning 가능
> - 주의
>   - 반환 값이 반드시 있어야 chaining 가능
>   - 없다면 콜백 함수가 이전의 promise 결과를 받을 수 없다.

### .catch(callback)

> - .then이 하나라도 실패하면 동작(python의  try, exception과 비슷)
> - 이전 작업의 실패로 생성된 error 객체는 catch 블록 안에서 사용할 수 있다.

### .finally(callback)

> - Promise 객체를 반환
> - 결과에 상관없이 무조건 지정된 콜백 함수가 실행된다.
> - Promise가 성공되었는지 거절되었는지 판단할 수 없기 때문에 어떠한 인자도 전달 받지 않는다.
> - 무조건 실행되어야 하는 절에서 사용 → .then과 .catch 블록에서의 코드 중복 방지

### Promise의 특징

> - 콜백이 event queue에 배치되는 엄격한 순서로 호출된다.
> - 비동기 작업이 성공하거나 실패한 뒤에 .then()메서드를 이용하여 추가한 경우에도 똑같이 동작한다.
> - .then()을 여러 번 사용하여 여러 개의 콜백을 추가할 수 있다.(`Chaning → 가장 뛰어난 장점`)

<br>

## Axios

- Promise based HTTP client for browser and Node.js

- 브라우저를 위한 Promise 기반의 클라이언트

- 요청에 특화되어 있음

- 리턴으로 Promise 객체를 받음

  → `promise based`이기 때문

- XHR보다 편리한 AJAX 요청이 가능하도록 도와준다.

  - 간편하게 쓸 수 있도록 라이브러리를 제공

- 사용할 때

  - axios 검색 : https://github.com/axios/axios
  - 설치할 때 첫번째 CDN을 쓸거임(Using jsDelivr CDN)

- 완벽하진 않음 → .then이 깊어질 수 있음 → async & await

<br>

## async & await

- .then chaining이 많아졌는데 문법적인 표현상으로 없애기 위해 등
- Vue에서는 공식적으로 Axios를 사용(Vue에서 만든 것은 아님)하고 있기 때문에 이걸 사용하지는 않을 예정.
- 기존 Promise 시스템 위에 구축된 syntactic sugar
  - syntactic sugar
    - 더 쉽게 읽고 표현할 수 있도록 설계된 프로그래밍 언어 내의 구문
    - 문법적 기능은 그대로 유지하는데 그것을 읽는 사람이 직관적으로 쉽게 코드를 읽을 수 있게 만든다.
- 새로운 문법(chaining 제거), 기능은 똑같다.