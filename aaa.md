# Web

``02.01``

## 1. HTML

: Hyper Text Markup Language

- Hyper Text
  - 정보가 동일 선상이 아니라 다중으로 연결되어 있음
  - ex) 1 - 2, 2 - 3이 아니라 1 - 3 으로 이동이 가능함
- Markup Language
  - 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어
  - 프로그래밍 언어와는 다르게 데이터만 표현
  - 웹 페이지를 작성하기 위한(구조를 잡기 위한) 언어
  - 웹 컨텐츠의 의미와 구조를 정의
- HTML로 작성된 문서파일 : .html



## 코드의 용도 및 목적

- title

  : 웹페이지의 이름을 정의할 때 사용

- body

  : html 화면을 구성할 때 사용

  - text, image, video 등 여러가지 종류의 구성 요소들을 감싸주는 Parents element



## Text 표현 방법

- div, span

  - 어떠한 기능, 의미도 없이 특정 영역을 css로 꾸미는 기능을 주고 싶을 때 사용

  - div : block 속성
  - span : inline 속성

- h1 ~ 6(heading)

  - 헤드라인 혹은 text의 제목을 강조할 때 사용

- p(paragraph)

  - text 형태의 정보를 입력할 때 사용

- br(break)

  - 단락을 줄바꿈 할 때 사용
  - closing tag가 없음

- em(emphasis)

  - 문장을 italic으로 강조할 때 사용

- strong

  - 문장을 bold로 강조할 때 사용

- ul(unordered list)

  - list 앞에 글머리 기호가 붙음

- ol(ordered list)

  - list 앞에 숫자형태로 기호가 붙음

- li(list)

  - 내용 입력시에 사용



### 웹페이지 링크 연결 방법

- a(anchor)
  - web page 에서 이동이나 web page에 내 화면을 연결할 때 사용
  - anchor 사이의 문자는 hyperlink의 이름이며 anchor 사이에 img code를 사용하면 text 형태가 아닌 image 형태의 hyperlink를 사용할 수 있다
- href(hyperlink reference)
  - anchor와 같이 사용하여 연결하고자 하는 경로를 활성화
  - url 입력시 각각의 페이지가 같은 폴더에 있다면 relative path를 대체해서 사용 가능하다. (href="./name.html)
- id
  - div와 함께 사용되며 구역별 정보를 제공하는 용도로 사용
  - a opening tag와 함께 사용하면 같은 화면에서 원하는 단락으로 이동할 수 있다. (href="#id")
- target
  - link로 연결된 웹브라우저를 어떤 형태로 열 것인지 정의(새탭 혹은 새창으로 열)



### Table 표현 방법

- table

  - table을 입력할 때 사용

- tr(table row)

  - table에 행을 추가할 때 사용

- td(table data)

  - table에 cell 값을 입력할 때 사용

- th(table heading)

  - table에 행/열의 이름을 정의할 때 사용하며 반드시 tr code안에 위치

  

## 2. form

: 정보를 수집할 때 사용하는 도구로 action이 처리되는 위치와 처리방식을 정의해주어 사용



### 코드의 용도 및 목적

- label
  - input 속성을 정의할 때 사용하며 둘 사이의 상호작용을 위해서는label에는 for 속성을 할당하고 input에는 id 속성을 할당
- input
  - 입력창을 만들때 사용

- type

  - 사용자가 입력한 정보의 유형을 정의할 때 사용

- name

  - 사용자가 입력한 정보를 서버로 전달할 때 정보의 이름 정의 목적으로 사용

- password

  - 사용자의 비밀번호 정보를 정의할 때 사용

- number

  - 사용자의 입력값을 숫자 형태로 정의할 때 사용

- range

  - 사용자의 입력값을 제한된 숫자 형태로 정의할 때 사용
  - input code에 min/max를 정의하면 해당 조건을 기준으로 입력값을 제한

- step

  - 입력된 number의 증/감 단위를 정의할 때 사용

- radio

  - 사용자가 1개의 값을 선택할 수 있는 기능을 제공

- check box

  - 사용자가 2개 이상의 값을 선택할 수 있는 기능을 제공

- value

  - 사용자가 정보를 입력하기 전에 입력이 필요한 정보의 미리보기 기능을 제공할 때 사용

- submit

  - 사용자가 입력한 정보를 서버로 전송할 때 사용

- require

  - input 속성과 같이 사용하여 필수로 입력되야 하는 정보가 입력될 수 있도록 경고문을 표현할 때 사용

- max/min

  - number type에서 입력값의 범위를 제한할 때 사용

- maxlength/minlength

  - text 형태로 표현되는 input 값의 글자수를 제한할 때 사용

- pattern

  - 사용자가 입력하는 정보가 일정한 pattern을 가진 형태일 때 사용
  - ex) 전화번호, 카드 번호
  - 

``0203``

- ```python
  # 정리
  Float
  - 본래는 이미지 좌,우측 주변으로 텍스트를 둘러싸는 레이아웃을 위해 도입
  - 더 나아가 이미지가 아닌 다른 요소들에도 적용해 웹사이트의 전체 레이아웃을 만드는데까지 발전 3가지의 값이 있음
  none : 기본값
  left : 요소를 왼쪽으로 띄움
  right : 요소를 오른쪽으로 띄움
      
  float는 block이 뜨게 하는 거라서 그 밑으로 
  block이 들어갈 수 있다.
  밑으로 들어가지 않게 하기 위해서는!
  (레이아웃이 깨지지 않게 하기위해)
  clearfix: 부모 부분에 넣어줌
  - 부모 이후에 가상요소를 만들거임(clearfix::after)
  - 내용이 비어있고(content: "";)
  - 디스플레이 블락(display: block);
  - 클리어 : float 무시, both(left, right 둘다)(clear both)
      
  Flexbox : CSS Flexible Box Layout
  요소 간 공간 배분과 정렬 기능을 위한 1차원(단방향) 레이아웃
  반드시 기억해야할 것!!!!
  1. 요소
  2. 축
  
  Bootsrap
  반응형 웹사이트를 빠르게 만들 수 있음프론트 엔드 개발에서 자주 쓰이는 기능들을 제공
  responsive grid system
  
  Grid system
  - flexbox로 제작됨
  - container, row, column
  - 반드시 기억 2가지!
  1. 12개의 column
   -> 적당한 크기이고, 약수가 많아서 약수가 많다 -> 다양하게 래이아웃을 짤 수 있음
  2. 6개의 Grid breakpoints(grid system을 치면 볼 수 있음)
  xs, sm, md, lg, xl, xxl 
  -> 픽셀을 외우는게 아니라 표를 봐야함
  grid는 무조건 container 안에서 진행해야함
  
  
  각각의 기술은 저마다 용도가 있고, 장단점이 있으며, 어떤 기술도 독립적인 용도를 갖추도록 설계되지는 않았다.
  특정 상황에 어떤 기술이 가장 적합한 도구가 될 것인지 파악하는 데에는 많은 경험이 뒷받침 되어야한다.
  ```

  ``02.04``

  ```python
  많이 쓰는 Component
  1. card
  2. Carousel
  3. Modal
  
  (word wrap 글자 줄바꿈 단위 설정, 글자/문자로 할지)
  
  col col 과 col-6 col-6은 같은 결과지만 원리는 다름
  col col : flex-glow 값이 같음(1)
  col-6, col-6 : width로 6/12 = 50% 
  width(%)는 부모의 넓이를 기준으로 차이하는 것을 말함
  
  @media : 화면크기에 따라서css 속성을 줄 수 있게
  옆에 ex)min-width:576 화면 크기가 최소 576 이상
  이면 적용한다.
  (미디어 커리라고 한다.)
  
  flex를 먹이면 block이 전체를 다 먹게 하지 않음
  아무것도 안주면 div는 block
  active로 하면 더 진하게 나옴
  w-100 부모의 크기에 맞춰줌(그림크기할때)
  ```


``02.05``

```python
우리가 지금까지 html, css, bootstrap을 한 이유
데이터(Django)를 '잘' 보여주기 위해서!

head - 정보를 가져오는 부분
orientation: landscape : 가로모드 - 가로가 더 긴 경우
@media에서 and 사용, or 대신 , 사용

ss에서 animation은 마진을 조정하는 것!
색, 크기 등도 바꿀 수 있다.(css안의 모든 요소)

참고!! 라이브러리 
- animate.css : animation site
    
폰트 검색(fonts.google.com), 폰트는 가독성을 위해 중요하다!
select this style 누르면 오른쪽에 주소가 나오고 (CDN)복사 후 title 밑에 붙여줌 &family=을 통해 여러개를 불러올 수 있음

icon을 쓸 때는 cdn을 복사해주고 Icon font란의 예시를 참고해서 작성
style=font-size ~ 하면 글자처럼 됨. color도 들어감.
i태그는 원래 이텔릭체의 의미였지만 현재 별로 안쓰기 때문에 icon을 많이 표현(inline)
참고!! fontawesome site
아이콘이 더 다양하다.
(무료 / 유료가 있음)
이메일 적으면 cdn 주소가 옴 그것을 적고 사용

form-aria-describedby : 접근성을 높이는 것
ex) image - alt 
- 그림을 못보는 사람들에게 도움을 줌.(몸이 불편한 사람들) 
네이버의 널리를 가면 체험 가능
```



:heavy_check_mark: **정리를 어떻게 할지 정해야 함!**

> - 이번주는 실습을 해보느라 제대로 정리를 못했음. 공부하면서 정리 필요!



## 기본구조

### 1. 요소(Element)

> : 여는/시작 태그와 닫는/종료 태그
>
> - HTML의 요소는 태그와 내용(contents)으로 구성
>
> #### 1.1 Head 요소
>
> > : 문서 제목, 문자 코드(인코딩)과 같이 해당 문서 정보를 담음
> >
> > - 브라우저에 나타나지 않음
> >
> > - 메타데이터(Open Graph Protocol)
> >
> >   : op라고도 하며, 검색시 홈페이지 밑에 head의 내용을 보여줌
>
> #### 1.2 Body 요소
>
> > : 브라우저 화면에 나타나는 정보로 실제 내용에 해당
> >
> > - DOM(Document Object Model) 트리
> >
> >   : 부모, 형제 관계속성(attribute)

### 2. 속성(Attribute)

> : 속성명과 속성값의 구조로 되어있음
>
> - 태그별로 사용할 수 있는 속성이 다름
>
> #### 2.1 시맨틱 태그(Semantic Tag)
>
> > : 태그에 의미를 부여, 사용 권장!
> >
> > - 의미가 명확해지고 읽기가 쉬움
> >
> > ##### 2.1.1 header
> >
> > > : 문서 전체나 섹션의 헤더(머릿말 부분)
> >
> > ##### 2.1.2 nav
> >
> > > : 내비게이션
> >
> > ##### 2.1.3 aside
> >
> > > : 사이드에 위치한 공간, 메인 콘텐츠와 관련성이 적은 콘텐츠
> > >
> > > - 여기에도 footer가 있을 수 있음
> >
> > ##### 2.1.4 section
> >
> > > : 문서의 일반적인 구분, 컨텐츠의 그룹을 표현
> >
> > ##### 2.1.5 article
> >
> > > : 문서, 페이지, 사이트 안에서 독립적으로 구분되는 영역
> >
> > ##### 2.1.6 footer
> >
> > > : 문서 전체나 섹션의 푸터(마지막 부분)
>
> #### 2.2 논 시맨틱 태그(Non Semantic Tag)
>
> > : 의미를 가지지 않음, 구조를 나누기 위해 사용
> >
> > ##### 2.2.1 div
> >
> > ##### 2.2.2 span



:memo: 텍스트 관련 요소

> - ``<b>`` : 그냥 굵게
> - ``<strong>`` : 굵게 + 의미 강조(시맨틱 요소)
> - ``<i>`` : 기울임
> - ``<em>`` : 기울임 + 추가적인 의미
> - ``<br>`` : 줄바꿈
> - ``<img>`` : 이미지 태그
> - ``autofocus`` : 웹 사이트 접속하자마자 그 위치로 포커싱이 됨
> - ``<hr>`` : 구분선
> - option*5 를 하면 한번에 5개가 생김



:memo: form 태그 : 가장 많이 사용

> ``<form>`` : 서버에서 처리될 데이터를 제공하는 역할
>
> - 브라우저 하는 일 : 주소창에
>   www.naver.com 치면 데이터가 나(브라우저)에 도착
>
>   데이터를 -> naver.com에 보내줘야 하는 일이 있음
>   이럴 때 form을 씀
>
> - input : 다양한 타입을 가지는 입력 데이터 필드
>
> - label : 서식 입력 요소의 캡션



:heavy_check_mark: **Tip!**

> - Python : 공식문서, 오버플로우
> - Web : 검색 뒤에 mdn ex) html a tag mdn, Can I Use



:satellite: **2spaces 설정**

> - ctrl shift p -> json 기본설정
>
> - 앞에 , 붙이고
>
>   ```python
>   "editor.tabSize": 2,
>       "[python]": {
>       "editor.insertSpaces": true,
>       "editor.tabSize": 4
>       }
>   ```



:memo: **이미지 넣을 때**

> : img 사용
>
> - alt는 설명 부분, 이미지가 잘못되었을 때도 이부분이 나와있음
> - 이미지를 넣을 때, 주소를 넣어도 되고 파일을 다운 받아서 이름을 적어도 됨



