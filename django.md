# Django

``03.08``

: Dynamic Web Application Program

- Static web
  - 미리 저장된 정적 파일(HTML, CSS, JS)을 제공
  - 서버에 사용자에게 보여질 것들이 미리 준비가 되어있고 사용자 요청이 들어오면 그대로 보여줌
- Dynamic web
  - 사용자에게 보여지는 클라이언트 사이드는 구현되어있고, 사용자 요청에 따라 서버 사이드쪽에서 일을 하여 다른 데이터를 만들어서 보여주는 것
  - 웹사이트에서 요청을 받았을 때, 서버는 추가적으로 무언가 일을 해서 클라이언트로 답장을 보내주는 것
  - 사용자 요청에 따라서 뒷단에서 일을 하여 보여준다고 이해!
  - 서버사이드 프로그래밍 언어들 즉, 우리가 일반적으로 알고 있는 언어들이 사용되고 그 언어들이 SQL이라고 하는 데이터베이스 언어를 통해서 데이터베이스 처리를 한다. 그 데이터들을 다시 잘 가공하여 클라이언트로 보여주는 것을 Dynamic website
  - 이런 Dynamic website를 만들어주는 framwork가 django
- 클라이언트(우리) : 브라우저를 통해서 돌아다니는데, naver의 sever에 메인페이지를 보내달라고 요청을 보냄  → 응답으로 naver에 대한 웹페이지 문서를 줌
- 웹의 프로토콜은 요청과 응답이 전부
- 서버단에서 운영되는 것을 django를 통해서 구축할 것임 - 요청을 받아서 응답을 보내는 서버 구축!

<br>

### django 동작

- web framework 
  - 웹페이지를 개발하는 과정에서 겪는 어려움을 줄이는 것이 주 목적
  - 기본적인 구조과 코드들을 기본적으로 제공해줌

- 파이썬으로 작성된 오픈소스 웹 어플리케이션 프레임워크로, 모델-뷰-컨트롤러 모델 패턴을 따르고 있다.

- 모델-뷰-컨트롤러(Model-View-Controller, MVC) : 소프트 웨어 디자인 패턴

- django는 MTV(Model-Template-View)라고 함 (똑같은 것을 용어를 바꾸어 표현)
  - Model : 데이터 베이스 관리 - 애플리케이션의 정보(데이터)
  - Template : 레이아웃(화면) - 텍스트, 체크박스 항목 등과 같은 사용자 인터페이스 요소, 사용자한테 보여지는 부분
  - View : 중심 컨트롤러(심장) - 데이터와 비즈니스 로직 사이의 상호동작 관리
  
- 장점 : 빠르다, 미리 로드 되어있다, 보안, 확장성

  ​	→ 쓸데없는 시간 낭비를 하지말고 웹을 작성하는데 도움을 준다.

- 장고 동작 과정

  - 클라이언트로부터 요청을 받는다.
  - Urls에서 요청을 받아서 어떤 요청인지 방향을 잡는다.
    - request를 알맞은 View로 전달
    - 장고는 서버 요청이 들어오면 요청이 어디로 가야하는지 인식하고 적절한 함수를 찾아서 함수를 호출시키는데 이러한 역할을 한다.
  - View가 Model로부터 데이터를 받고 처리를 해서 템플릿에서 템플릿을 받아서 하나의 완성된 문서를 저장한다. 
  - 최종적으로 응답을 넘겨준다(형식은 어떤 것일지 모름), 이 응답이 우리가 받는 결과물

<br>

- firstpjt
  - ``__init__.py`` : 하나의 package로 인식할 수 있게 해준다.  - 수정 X
  - ``asgi.py`` : 나중에 비동기적인 웹서버와 연동할 때 사용 - 지금은 수정 X
  - ``settings.py`` : 웹사이트의 모든 설정을 포함, 우리가 만든 어플리케이션 등록, 파일들의 위치, 데이터베이스의 세부사항, 보안에 관련된 사항 등이 작성되어 있음 - 많이 수정할 예정  // 중요!!
  - ``url.py`` : 사이트 내부의 url 연결을 해주는 역할 // 중요!!
  - ``wsgi.py`` : 배포할 때 도움을 준다.

- 사이트가 실제로 기능적인 측면을 하기 위해서는 이 프로젝트가 하는 것이 아니라 application이 이러한 동작을 한다.
- articles
  - ``admin.py`` : 관리자 사이트를 커스텀하는 파이썬 파일 // 중요!!
  - ``apps.py`` :앱에 대한 정보가 들어있는 파일 - 수정 X
  - ``models.py`` : 많이 사용할 예정 // 중요!!
  - ``tests.py`` : test code를 작성하는 곳 - 사용 안할 예정
  - ``views.py`` : 중간 관리자의 역할 // 중요!!



- 장고의 하나의 프로젝트는 여러가지 애플리케이션을 가지고 있는데 동일선상에 만들어짐
- 애플리케이션이 만들어져도 프로젝트 입장에서는 알 수가 없기 때문에 만들었음을 알려주기 위해서 프로젝트에 등록을 해주어야함



- admin page를 기본적으로 제공해준다(django의 강점)
- 

<br>

## DTL(Django Template Language)

- django template에서 사용하는 built-in template system
- 조건문, 반복문, 치환, 필터 등의 기능을 제공한다.
- Python코드와 비슷하게 작성(이 코드가 Python에서 실행되는 것은 아님!)
- 사용자에게 보여줄 데이터를 가공하는 작업이 필요할 경우, DTL에 내장된 연산 방식을 사용하지 말고, 되도록이면 뷰 하수 내부에서 데이터를 가공한 뒤 템플릿에게 넘겨주는 것 추천!

#### DTL Syntax

- Variable
  - {{ variable }}
  - reder()를 사용해서 views.py에서 정의한 변수를 template파일로 넘겨서 사용(세번째 인자)
  - 변수명은 영어, 숫자, 밑줄(_) 사용 가능
  - 밑줄 시작 x, 공백 사용 x
  - dot(.)을 사용하여 변수 속성에 접근 가능

- Filters
  - {{ variable|filter }}
  - 표시할 변수를 수정할 때 사용
- Tags
  - {% tag %}
  - 출력 텍스트를 만들거나, 반복 또는 논리를 수행하여 제어 흐름을 만드는 변수보다 복잡한 일을 수행
  - 일부 태그는 시작과 종료 태그가 필요
- Comments
- 줄의 주석 : {# string #}
- 여러줄 주석 : {% comment %}  {% endcomment %}

<br>

## Template inheritance(템플릿 상속)

- 코드의 재사용성에 초점을 맞춤
- tags
  - {% extends '부모템플릿의 경로' %}
  - {% block %}  {% endblock %} : 여러개가 있을 수 있음
    - content는 닫히는 것을 구분하려고 씀, 하나면 쓸 필요 없음
- project - settings - DIR - BASE_DIR로 변경 (/로 경로가 넘어감)

<br>

## 보충수업(유창오 교수님)

1. 프로젝트 생성하기

   ```shell
   $ django-admin startproject 프로젝트 이름
   ```

2. 앱 생성하기

   ```shell
   # manage.py가 있는 경로에서 해야한다. manage.py한테 명령하는 것이기 때문에
   $ python manage.py startapp 앱이름
   ```

   ```django
   프로젝트 이름/
   	프로젝트 폴더/
   	앱폴더/
   	manage.py
   ```

3. 기본설정(settings.py)

   - 등록

4. URL 분리

   - include

5. 템플릿 상속

   - 중복 코드 방지
   - TEMPLATES - DIRS

6. `urls.py`

7. `viesw.py`

8. `templates`

<br>

## MTV

- Model : DB 관리
- Template : 화면

- View : 중간 관리자

<br>

<hr>

:cherries: TIP

> - `django-admin startproject muyaho .` : 현재폴더에 생성

<br>

:heavy_check_mark: 써야하는 것

> - 요청 뒤에는 /(엔드 슬래시)
> - context 값은 dictionary로 넘어간다!

<br>

:checkered_flag: 스타일 가이드

> - {{ variable }} 괄호에 붙이지 않기 