# Vue

# `05.06`

## Front Framework가 나온 이유

- Vue.js, React, Angular 등

- 과정의 불편함

  - 데이터가 변하고 그 데이터에 연동된 엘리먼트를 가져오고 엘리먼트의 내부를 바꿔주는 과정을 반복하는 것이 불편함

  → 데이터가 변하면 나머지를 해주는 프레임워크 등장

<br>

# `vue 문법 정리 필요!` 

<br>

<br>

# 05.07

## 알고리즘 왜 적용시켜야할까

- 어떤 목적을 달성하기 위해 도출하기 위한 과정(유의미한 결과를 만들어내는 과정)
- 효율적인 코드를 작성(속도 개선)

<br>

<br>

# `05.10`

# SFC(Single File Component)

- 하나의 파일로 구성하면 변수 관리와 코드의 유지 보수가 어렵다.
- → 각 기능별로 나눠서 개발하면 처음에 준비할 때는 어렵지만 사이트가 커질수록 변수 관리와 유지 보수가 좋다, 한 화면 안에서 여러가지 컴포넌트가 존재
- 컴포넌트로 개발한다는 것은 하나의 파일을 의미하는 것은 아니라 하나의 파일 안에 여러가지 컴포넌트가 들어갈 수 있다는 것을 말한다.(.vue 확장자를 가진 싱글 파일 컴포넌트를 통해 개발하는 방식)
- Vue는 SFC 개발을 사용한다.(.vue 파일 하나가 하나의 컴포넌트 역할)
- Vue의 컴포넌트 기반 개발의 핵심 특징
- 화면의 특정 영역에 대한 HTML, CSS, JavaScript 코드를 하나의 파일(.vue)에서 관리
- 하나의 컴포넌트는 .vue라는 하나의 파일 안에서 작성되는 코드의 결과물

<br>

## Component(컴포넌트)

- 특정 기능을 하는 코드 블럭을 만들어 놓으면 다른 곳에서도 재사용 할 수 있다.

  → 컴포넌트는 개발을 함에 있어 유지보수를 쉽게 만들어 줄 뿐만 아니라, 재사용성의 측면에서도 매우 강력한 기능을 제공한다.
  
- Vue 컴포넌트 === Vue 인스턴스

  ex) const app

<br>

# Vue cli

개발을 하다보니 하나의 파일에서 모든 코드를 작성하는 것이 너무 어렵다.

→ 파일을 분리해서 작성

→ 많으면 수백, 수천개의 파일이 만들어짐 → a.js, b.js ... z.js ... 전부를 받아와야 응답하는 index.js를 보여줄 수 있음 → 개발은 나눠서 하는 게 좋고 속도는 하나의 파일이 좋다 !

⇒ 하나로 묶어서 만들어주는 것 webpack(bundler), 변수이름도 안겹치게 해줌 → 설정이 어렵다 → vue-cli를 만듦(ex. 장고의 django-admin startproject) : vue의 개발환경을 세팅해준다

⇒ 개발환경을 세팅해주고 하나로 묶어서 서빙해준다.

- http는 연결횟수가 작을수록 좋다(같은 용량이라도 하나의 파일이면 빠름)
- 요청에 따라 내 컴퓨터에 담긴 파일을 전송해주는 서버를 만들고 + workshop.html을 태우는게  유리하다. (기존의 workshop.html의 주소는 파일의 주소임)
- vue-cli 안에 있는 개발용 웹서버가 localhost 8080을 만들어준다.
- Vue.js 개발을 위한 표준 도구
- 프로젝트의 구성을 도와주는 역할을 하며 Vue 개발 생태계에서 표준 tool 기준을 목표로 한다.

<br>

## Node.js

- `JavaScript Runtime Environment`

- 단순히 브라우저에서만 작동할 수 있었던 JS를 밖에서도 사용할 수 있게 만들어준다.(여러 OS 환경에서 가능하게) → 자바스크립트 언어의 태생적 한계를 해결함

- 설치 참고 : https://cli.vuejs.org/guide/installation.html

  ```python
  # 참고
  
  vue 파일을 만들때는 git bash가 아니라 vscode로 진행
  git bash로 하면 선택할때 화살표를 움직일 수가 없음 → 인터렉티브 터미널이 아니기 때문에
  처음에 vue create를 한 후, 서버를 키려면 이동해야한다. cd로 이동한 후 작업 시작 !
  ```

<br>

## NPM(Node Package Manager)

- 자바스크립트 언어를 위한 패키지 관리자
  - python의 pip
- Node.js와 함께 자동으로 설치된다.

<br>

## Vue CLI 설치

- vue-cli 설치

  `$ npm install -g @vue/cli`

- 버전 확인

  `$ vue --version`

- 프로젝트 생성

  `$ vue create pjt-name`

- run server

  `$ npm run serve`

<br>

# Babel & Webpack

## Babel

- `Compiler`

- JavaScript Transcomiler

- JS는 표준화의 영향으로 작성된 코드의 스펙트럼이 매우 다양하다.

- 같은 의미의 코드인데 문법이 안맞아서 다시 작성해야하는 일이 있음 → 이러한 문제를 해결하기 위해 사용한다.

- 원시코드(최신 버전)를 목적 코드(구 버전)으로 옮기는 번역기

  ex) ES2015 → ES5로 compile

- 구버전을 사용하는 애플리케이션을 대응

- 기본적으로 babel 설정이 되어있음

<br>

## Webpack

- `static module bundler`
- 모듈 간의 의존성 문제를 해결하기 위한 도구

<br>

## Module

- 단지 파일 하나를 의미

  ex) 스크립트 하나 === 모듈 하나

- 의존성 문제 → 처음에 등장했던 이유는 JS, app이 커져서 등장했는데 모듈의 수가 점점 많아짐, 의존성이 깊어짐(ex. 4.2버전에서만 동작) → 문제가 발생하면 어떤 모듈 간의 문제인지 파악하기 어려워짐 ⇒ Webpack 등장 : 모듈간의 의존성을 해결하기 위해

<br>

## Bundler

- 모듈 의존성 문제를 해결해주는 작업이 Bundling, 이러한 일을 해주는 도구가 Bundler
- Webpack은 다양한  Bundler 중 하나(많은 개발자들이 사용)
- 모듈들을 하나로 묶어주고 파일은 하나(혹은 여러개)로 만들어진다.
- Bundling된 결과물은 더 이상 순서에 영향을 받지 않고 동작하게 된다.
- Bundling 과정에서 문제가 해결되지 않으면 최종 결과물을 만들어 낼 수 없기 때문에 유지 & 보수의 측면에서도 편리해진다.
- Vue CLI는 Babel, Webpack에 대핸 초기 설정이 자동으로 되어있다.

<br>

## Vue cli 구성

### babel.config.js

> - 바벨 설정과 관련된 것들

### node_modules

> - Webpack이 들어가있음
> - node.js 환경의 여러 의존성 모듈

### public

> - favicon은 우리가 아는 favicon
> - index.html : 뼈대가 되는 html - runserve때 켜지는 것

### src

> - assets : Webpack에 빌드되는 정적인 파일들
> - components : 하위 컴포넌트 파일들이 들어감
> - App.vue : 뷰에서 최상위 컴포넌트
> - 주로 작업하는 공간

### main.js

> - Webpack이 빌드를 시작할 때 가장 먼저 불러오는 시작점(entry point)
> - 실제 단일 파일에서 DOM과 data를 연결했던 것과 동일한 작업이 이루어지는 곳
> - Vue의 전역에서 사용할 수 있는 모듈을 등록할 수 있음

### package.json

> - scripts : 사용할 명령어 script
> - dependencies : 개발환경과 프로젝트 레벨에서까지 사용
> - devDependencie : 개발환경에서 사용하는 모듈(requirements.txt와 비슷)

### package-lock.json

> - 동일한 종속성을 유지하기 위해 도와줌, 배포, 개발할 때
> - 개발 과정 중에 의존성 충돌 방지
> - 모든 의존성을 가지는 패키지를 명시 (`$npm ls`), 설정 및 관리

### .gitignore

> - gitignore

<br>

# Pass Props & Emit Events

- 부모는 자식에게 데이터를 전달(Pass props)하며, 자식은 자신에게 일어난 일을 부모에게 알림(Emit event)
  - 부모와 자식이 명확하게 정의된 인터페이스를 통해 격리된 상태로 유지할 수 있다.
  - 단방향, 디버깅, 유지 보수에 좋다.
- props : 아래로, event : 위로

## Props

- 상위 컴포넌트의 정보를 전달하기위한 사용자 지정 특성
- 하위 컴포넌트는 props 옵션을 사용하여 수신하는 props를 명시적으로 선언해야 한다.
- 데이터는 props 옵션을 사용하여 하위 컴포턴트로 전달된다.
- 하위 컴포넌트의 템플릿에서 상위 데이터를 직접 참조할 수 없다.
- 이름
  - HTML : kebab-case
  - script : camelCase

## 단방향 데이터 흐름

- 모든 props는 하위 속성과 상위 속성 사이의 단방향 바인딩을 형성
- 부모의 속성이 변경되면 자식 속성에서 전달되지만, 반대 방향으로는 안된다.
  - 자식 요소가 의도치 않게 부모 요소의 상태를 변경함으로써 앱의 데이터 흐름을 이해하기 어렵게 만드는 일을 막기 위해서
- 부모 컴포넌트가 업데이트될 때마다 자식 요소의 모든 prop들이 최신 값으로 업데이트 된다.

## Emit event

- $emit(event)
  - 현재 인스턴스에서 이벤트를 트리거
  - 추가 인자는 리스너의 콜백 함수로 전달
- 부모 컴포넌트는 자식 컴포넌트가 사용되는 템플릿에서  v-on을 사용하여 자식 컴포넌트가 보낸 이벤트를 청취(v-on을 이용한 사용자 지정 이벤트)
- event 이름
  - 컴포넌트 및 props와는 달리, 이벤트는 자동 대소문자 변환을 제공하지 않는다.
  - HTML의 대소문자 구분을 위해 DOM 템플릿의 v-on 이벤트 리스너는 항상 자동으로 소문자 변환되기 때문에 v-on:myEvent는 자동으로 v-on:myevent로 변환
  - 이러한 이유로 이벤트 이름에는 kebab-case를 사용하는 것을 권장한다.

<br>

# Vue Router

- Vue.js의 공식 라우터
- `Vue Router` 참고 : [Vue Router](https://router.vuejs.org/kr/guide/)
- url이 갈 수 있는 경로들을 결정
- `vue add router` : router는 CLI를 사용할 경우에는 프로젝트마다 추가해주는 것
- SPA상에서 라우팅을 쉽게 개발할 수 있는 기능을 제공한다.
- SPA의 장점 → url이 변경되지 않는다 !
- 사용자 경험을 위해 `History API`를 이용해서 router를 구현
- 브라우저의 히스토리는 남기지만 실제 페이지는 이동하지 않는 기능을 지원
- 이것을 통해 뒤로 가기, 앞으로 가기가 가능
- `History` 참고 : [History](https://developer.mozilla.org/ko/docs/Web/API/History)
- 페이지를 이동하는 경험을 주지만 사실은 새로운 컴포넌트를 주는 것
- `url이 움직일 수 없다는 단점을 해결하기 위해 등장`
- 멈춰있는 듯한 경험을 움직이게 보여줌 → url에 바뀌지 않으면 사용자가 멈춰있다라는 느낌을 들게 함, 이를 해결하기 위해 다른 컴포넌트를 볼 때 페이지가 이동했다는 느낌을 주게 함
- 페이지를 렌더링하는거랑 컴포넌트를 렌더링 하는거랑 큰 차이 → 서버로 요청을 보내는 것 여부(페이지 렌더링 : 서버로 요청)

<br>

## router-link

- index.js 파일에 정의한 경로에 등록한 특정한 컴포넌트와 매핑한다.
- a 태그지만 우리가 알고 있는 GET 요청을 보내는 a 태그와 조금 다르게 기본 GET 요청을 보내는 이벤트를 제거한 형태로 구성된다.

<br>

## router-view

- 실제 component가 DOM에 부착되어 보이는 자리를 의미
- router-link를 클릭하면 해당 경로와 연결되어 있는 index.js에 정의한 컴포넌트가 위치한다.

<br>

## Component vs views

- 컴포넌트를 만들어 갈 때 정해진 구조가 있는 것은 아니다.
- App.vue
  - 최상위 컴포넌트
- views
  - router(index.js)에 매핑되는 컴포넌트를 모아두는 폴더
- components
  - router에 매핑된 컴포넌트 내부에 작성하는 컴포넌트를 모아두는 폴더

<br>

## History mode

- HTML history API를 사용해서 router를 구현한 것
- 브라우저의 히스토리는 남기지만 실제 페이지는 이동하지 않는 기능을 지원한다.

<br>

## Vue Router가 필요한 이유

- SPA 등장 이전에는 서버가 모든 라우팅을 통제하고 요청 경로에 맞는  HTML을 제공했다.
- SPA 등장 이후에는 서버는 index.html 하나만 제공하고 이후 모든 처리는 HTML 위에서 JS 코드를 활용해 진행했다. → 요청에 대한 처리를 더 이상 서버가 하지 않음
- 라우팅 처리 차이
  - SSR
    - 라우팅에 대한 결정권을 서버가 가짐
  - CSR
    - 클라이언트는 더 이상 서버로 요청을 보내지 않고 응답 받은 HTML 문서안에서 주소가 변경되면 특정 주소에 맞는 컴포넌트를 렌더링
    - 라우팅에 대한 결정권을 클라이언트가 가짐
- Vue Router는 라우팅의 결정권을 가진 Vue.js에서 라우팅을 편리하게 할 수있는 Tool을 제공해주는 라이브러리이다.

<br>

## :heavy_check_mark: 참고

- npm으로 설치하면 자동으로 package에서 알아서 수정해줌, (삭제도) → 따로 관여 x

- 만들면 자동으로 git init이 선언됨(master가 붙어있음)

- .vue 하나가 component 하나 !

#### `<script scope>`, `<script>` 차이점

> - scope를 적용 안하면 하위 컴포넌트까지 적용
> - 적용 되어있으면 그 컴포넌트만 적용 !

<br>

## 웹서버 / 웹애플리케이션서버

- 웹서버 기본 역할 중 하나 : 내 컴퓨터에 있는 파일을 요청자에게 응답으로 전송해주는 것

- 웹애플리케이션서버 : 웹서버에 장착할 수 있는 확장팩 느낌, ex) django

- 웹애플리케이션서버 하는 일 : db관리, url, body(뭐가 적혀있는지), method, 쿠키 인증여부 등에 따라서 동작하고 그에 맞는 응답을 만들어서 주는 프로그램

→ 사용자의 응답으로 index.html, index.js, style.css만 주면 된다면 웹서버 하나만 있어도 됨

<br>

<br>

`05.12`

# Vuex

- statement management pattern + library for vue.js
  - `상태` 관리 패턴 + 라이브러리
- 상태를 `전역 저장소`로 관리할 수  있도로고 지원하는 라이브러리
  - state가 예측 가능한 방식으로만 변경될 수 있도록 보장하는 규칙 설정
  - 애플리케이션의 모든 컴포넌트에 대한 `중앙 집중식 저장소` 역할
- Vue의 devtools와 통합되어 기타 고급 기능을 제공
- 전역에 있는 어딘가에서 데이터를 관리

<br>

## State

- data이며 해당 어플리케이션의 핵심이 되는 요소
- 각 컴포넌트에서 관리(.html : new Vue({}), SFC : .vue)
- DOM은 data(state)에 반응하여 DOM을 렌더링

<br>

## Pass props & Emit event

- 각 컴포넌트는 독립적으로 데이터를 관리
- 데이터는 단방향 흐름으로 부모 → 자식 간의 전달만 가능하며 반대의 경우 이벤트를 통해 전달
- 장점
  - 데이터의 흐름을 직관적으로 파악 가능
- 단점
  - 컴포넌트 중첩이 깊어지는 경우 동위 관계(형제끼리)의 컴포넌트로의 데이터 전달이 불편해짐(위로 올려서 전달)

<br>

## in Vuex

- 중앙 저장소에서 state를 모아놓고 관리
- 규모가 큰 (컴포넌트 중첩이 깊은) 프로젝트에 매우 편리
- 각 컴포넌트에서는 중앙 집중 저장소의 state만 신경 쓰면 됨
- 이를 공유하는 다른 컴포넌트는 알아서 동기화

<br>

# Vuex Core Concept

## 단방향 데이터 흐름

- 상태(state)는 앱을 작동하는 원본 소스(data)
- 뷰(view) 상태의 선언적 매핑(보여지는 부분)
- 액션(action)은 뷰에서 사용자 입력에 대해 반응적으로

<br>

### 단방향 데이터 흐름의 단점

> - 공통의 상태를 공유하는 여러 컴포넌트가 있는 경우 빠르게 복잡해짐
> - ex) 지나치게 중첩된 컴포넌트를 통과하는 prop

<br>

## 상태 관리 패턴

- 컴포넌트의 공유된 상태를 추출하고 이를 전연에서 관리 하도록 함
- 컴포넌트는 커다란 뷰가 되며 모든 컴포넌트는 트리에 상관없이 상태에 엑세스 하거나 동작을 트리거 할 수 있음
- 상태 관리 및 특정 규칙 적용과 관련된 개념을 정의하고 분리함으로써 코드의 구조와 유지 관리 기능 향상
- 단방향 데이터 흐름이 중대형 프로젝트에서 발생할 수 있는 문제점을 해결

<br>

## Vuex 구성 요소

- State
- Actions(method와 비슷)
- Mutations
- Getters
- Module

<br>

### State

> - 중앙에서 관리하는 모든 상태 정보 (data)
> - Mutation(하나의 공간에 변경할 수 있는 메서드를 정의)에 정의된 메서드에 의해 변경 → 상태를 변경(Mutaton에 의해 조작)
> - 다이렉트로 변경하지 않고 Mutation을 이용해서 변경
> - 여러 컴포넌트 내부에 있는 특정 state를 중앙에서 관리
>   - 이전의 방식은 state를 찾기 위해 각 컴포넌트를 직접 확인
>   - Vuex Store에서 컴포넌트에서 사용하는 state를 한 눈에 파악 가능
> - state가 변화하면 해당 state를 공유하는 컴포넌트의 DOM은 알아서 렌더링
> - 컴포넌트는 Vue store에서 state 정보를 가져와 사용
> - `dispatch()` 를 사용하여 Actions 내부로 호출 사용
> - `$store.state` , $가 붙은 것은 private한 속성(지정된 규칙에 따라 접근해서 변경)

### Actions

> - Component에서 dispatch() 메서드에 의해 호출
> - Backend API와 통신하여 Data Fetching 등의 작업을 수행
>   - 동기적인 작업 뿐만 아니라 `비동기적인 작업을 포함 가능`
> - 항상 context가 인자로 넘어옴
>   - store.js 파일 내에 있는 모든 요소에 접근해서 속성 접근 & 메서드 호출이 가능
>   - 단, `(가능하지만) state를 직접 변경하지 않음`
>   - state에 들어가 있지 않은 다른 데이터들을 처리
>   - 가져올 때 { commit } 가능하다.
>     - `JS destructuring` 참고 : [JS destructuring](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
> - mutations에 정의된 메서드를 `commit` 메서드로 호출
> - state는 오로지 mutations 메서드를 통해서만 조작
>   - 명확한 역할 분담ㄷ을 통해 서비스 규모가 커져도 state를 올바르게 관리하기 위함

### Mutations

> - `Actions에서 commit() 메서드에 의해 호출`
> - 비동기적으로 동작하면 state가 변화하는 시점이 달라질 수 있기 때문에 `동기적인 코드만 작성`(상태가 변화하는 시점을 정확하게 하기 위해), 값이 있을 때 저장
> - 비동기 코드를 동작 시킬 수는 있지만 저장하는 시점이 달라질 수 있으므로 동기적인 코드만 작성
> - mutations에 정의되는 메서드의 첫 번째 인자로 state가 넘어옴
>
> actions와 mutations의 공통점 : 둘 다 내부에 메서드가 있다.
>
> 비동기와 동기를 따로 두는 이유?
>
> - ex) 페이지를 불러오는 시점에 저장이 안되어 있으면 비어있는 경우가 발생
>   - state에 title과 content가 있고, title : 동기, content : 비동기라면, 페이지가 보여질 때 비동기 작업이 끝나지 않으면 title만 보였다가 비동기 작업이 끝나면 보여질 수 있음

### Getters

> - state를 변경하지 않고 활용하여 계산을 수행(computed와 유사)
>   - 실제 계산된 값을 사용하는 것처럼 getterts는 저장소의 상태(state)를 기준으로 계산
>   - ex) state에 todo list의 해야 할 일의 목록의 경우 todo가 완료된 목록만 필터링해서 보여줘야 하는 경우가 이음
>   - getters에서 computed의 값이 true인 요소가 필터링 해서 계산된 값을 담아 놓을 수 있음
> - getters 자체가 state 자체를 변경하지는 않음
>   - state를 특정한 조건에 따라 구분(계산)만 함
>   - 계산된 값을 가져옴
>   - state를  변경하는 것은 Mutations만 !

### Module

> - store가 커졌을 때 주로 사용

<br>

## :heavy_check_mark: 참고

- Vue cli에 Vuex를 추가할 때는 `vue add vuex`
- trim : 좌우 공백을 제거한다.
- 순서
  1. 컴포넌트에서 `dispatch`를 활용해 actions를 호출
  2. action에 정의된 메서드는 commit을 활용해 mutations를 호출
  3. mutation에 정의된 메서드는 state를 조작한다.
- js 파일 실행할 때
  - node를 깔았기 때문에 (자바스크립트의 런타임 환경) vscode에서 실행가능
  - `node 파일이름` 로 실행
- 상태관리가 너무 어려워졌을 경우에 Vuex를 사용
- 상태 : 로딩중, 로딩완료, 등도 데이터로 표현 가능하고, 화면에 나타내는 어떤 변화 같은 걸 다 데이터로 관리하는 것
- 네트워크가 통신하는 방법 → 면접 당골
  - `CORS` 참고 : [교차 출처 리소스 공유](https://developer.mozilla.org/ko/docs/Web/HTTP/CORS)
- Router는 필요할 때 사용
- Pass props & Emit event // Vuex 중에 선택해서 사용

### 상태가 선언되는 공간

> - 기존에는 Data
> - Vuex에서는 state

### 상태를 수정하는 공간

> - 기존에는 methods, created
> - Vuex에서는 mutations

### 활용해서 작업하는 공간

> - Vuex에서는 actions

<br>

## 추가 활용

- js indexOf
  - https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf
- js splice
  - https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/splice
- js spread
  - https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Spread_syntax

<br>

## Vuex 바인딩 헬퍼

- `바인딩 헬퍼` 참고 : [바인딩 헬퍼](https://vuex.vuejs.org/kr/api/#컴포넌트-바인딩-헬퍼)
- mapState
  - computed와 state를 매핑
- mapGetters
  - computed와 getters 매핑
- mapActions

<br>

## 브라우저의 로컬 스토리지

- 쿠키나 세션 저장하는 공간임

- 여기에 저장해서 새로고침해도 날아가지 않게

- `vuex persistedstate` 참고 : [vuex persistedstate](https://www.npmjs.com/package/vuex-persistedstate)

  ```vue
  npm i vuex-persistedstate
  
  import createPersistedState from "vuex-persistedstate"
  
  plugins: [
  
  createPersistedState(),
  
  ],
  ```

<br>

# CS 핵심이론

- 컴퓨터(시스템)에 대한 이해 (컴퓨터와 제대로 소통하기)

- 자료구조, 알고리즘 활용법 (일의 효율을 높이기)

- Coder에서 Developer로 성장

- 기업목적에 따른 기본적 CS 지식이 필요 ( 게임회사, SNS회사에 필요한 지식이 다름)

