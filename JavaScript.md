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

  