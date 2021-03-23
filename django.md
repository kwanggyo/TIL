# Django

``03.08``

: Dynamic Web Application Program

- Static web
  - 미리 저장된 정적 파일(HTML, CSS, JS)을 제공
  - 서버에 사용자에게 보여질 것들이 미리 준비가 되어있고 사용자 요청이 들어오면 그대로 보여줌
- Dynamic web
  - 사용자에게 보여지는 클라이언트 사이드는 구현되어있고, 사용자 요청에 따라 서버 사이드쪽에서 일을 하여 다른 데이터를 만들어서 보여주는 것
  - 웹사이트에서 요청을 받았을 때, 서버는 추가적으로 무언가 일을 해서 클라이언트로 답장을 보내주는 것(서버단에서 운영하는 것 - Django 사용)
  - 사용자 요청에 따라서 뒷단에서 일을 하여 보여준다고 이해!
  - 서버사이드 프로그래밍 언어들 즉, 우리가 일반적으로 알고 있는 언어들이 사용되고 그 언어들이 SQL이라고 하는 데이터베이스 언어를 통해서 데이터베이스 처리를 한다. 그 데이터들을 다시 잘 가공하여 클라이언트로 보여주는 것을 Dynamic website
  - 이런 Dynamic website를 만들어주는 framwork가 django
- 클라이언트(우리) : 브라우저를 통해서 돌아다니는데, naver의 sever에 메인페이지를 보내달라고 요청을 보냄  → 응답으로 naver에 대한 웹페이지 문서를 줌
- 웹의 프로토콜은 요청과 응답이 전부
- 서버단에서 운영되는 것을 django를 통해서 구축할 것임 - 요청을 받아서 응답을 보내는 서버 구축!

<br>

## django 동작

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

#### 설치과정

> ```shell
> $ pip install django
> ```
>
> - pip list를 했을 때, 장고가 있으면 됨(3.1 이상)

#### 시작 과정

> ```shell
> $ django-admin startproject firstpjt(프로젝트이름)
> ```
>
> - 폴더에 firstpjt 폴더가 생성되고 폴더안에서 vscode를 킨다.
> - 프로젝트 이름으로 built-in, 함수이름, hyphen(-) 등을 쓰면 안된다.
>
> ```shell
> $ python manage.py runserver
> ```
>
> - 서버를 킴(웹 페이지에서 볼 수 있음)
> - ctrl + c를 통해 끌 수 있다.
>
> ```shell
> $ python manage.py startapp articles(앱이름)
> ```
>
> - articles라는 앱을 생성
>
> - 어플리케이션이 만들어졌다는 것을 알려주기위해 firstpjt - settings에 들어가서 INSTALLED_APPS의 제일 위에 articles, 를 적어준다.
> - 일반적으로 웹 오더의 순서를
>   - local apps(articles 같은것)
>   - 3rd-party apps
>   - django apps(이미 설치되어있는 기본 앱들)
> - internationalization의 language_code: 'ko-kr', Time_zone: Asia/Seoul 로 설정
>   - 구글에 database time zones로 검색

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
- 실제적으로 처리하는 것은 어플리케이션들이 담당한다.
- 애플리케이션이 만들어져도 프로젝트 입장에서는 알 수가 없기 때문에 만들었음을 알려주기 위해서 프로젝트에 등록을 해주어야함
- admin page를 기본적으로 제공해준다(django의 강점)



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
    - 자식템플릿이 부모템플릿을 확장한다는 것을 알림
    - 반드시 템플릿의 **최상단**에 위치해야함
  - {% block %}  {% endblock %} : 여러개가 있을 수 있음
    - content는 닫히는 것을 구분하려고 씀, 하나면 쓸 필요 없음
    - 여기에 추가할 부분 작성(원하는 구역에)
- project - settings - DIR - BASE_DIR로 변경 (/로 경로가 넘어감)

<br>

## Django template system(설계 철학)

- 표현과 로직(view)을 분리
  - 템플릿은 표현만!
  - 가공과 로직은 views.py
- 중복을 배제
  - 템플릿 상속

<br>

## 데이터를 받을 때(사용자의 입력을 받을 때)

### HTML form

- 웹에서 사용자 정보를 입력하는 방식(text, button, checkbox, image 등)을 제공
- 사용자로부터 할당된 데이터를 서버로 전송하는 역할을 담당
- 핵심 속성
  - action : 입력 데이터가 전송될 URL 지정, ex. '/catch/'
  - method : 입력 데이터 전달 방식 지정
    - default : GET
    - GET : url의 parameter로 데이터를 넘김, data에 손을 대지는 않고 가져오기만 함
- 접근을 할 때 request.GET.get[key값]으로 접근! (GET에 있는 dict의 값을 가져와야하기 때문)
  - **요청하는 데이터 값에 어떻게 접근하여 가져올 것인지가 핵심!!**

### HTML input

- 사용자로부터 데이터를 입력 받기 위해 사용
- 핵심속성
  - name : 데이터의 키(서버의 입장에서는 데이터의 키에 접근을 해야함)
  - 사용자가 입력하는 값은 value로 넘어간다. 이때 서버는 value에 붙은 key에 접근해야 함
  - ?key=value&key=value형태로 전달

### HTTP

- Hyper Text Transfer Protocol (+ S(secure))

- 웹에서 이루어지는 모든 데이터 교환의 기초

- request method : GET, POST, PUT, DELETE

  - GET

    - 서버로부터 정보를 **조회**하는데 사용
    - 데이터를 가져올때만 사용해야 함

    - 데이터를 서버로 전송할 때 body가 아닌 Query String Parameters를 통해 전송
      - Query String Parameters는 URL 뒤에 붙어서 넘어간다는 것, body에 들어가면 URL에 뜨지 않음

<br>

## URL

- **URL을 통한 클라이언트의 요청에서부터 시작** 됨
  - 항상 urls.py를 시작으로 작성해줬음

#### URL mapping

- app, path가 많아지면 **유지보수**가 힘들기 때문에 분리하는 것!
- 각 app에 url.py를 작성
  - urlpatterns = [] 는 주소가 없더라도 있어야함
  - 연결할 때는 project의 urls.py에 path('app_name/', include('app_name.urls.py')) 이런식으로 넘겨준다. (중앙 컨트롤타워 같은 역할)

#### Naming URL patterns

- 링크에 url을 직접 작성하는 것이 아니라 path 함수의 name 인자를 정의해서 사용

- url을 하드코딩 하는 것이 아니라 이름을 붙이는 것, ex) name='index'

  ```python
  path('index/', views.index, name='index')
  ```

  ```django
  <a herf={% url 'index' %}>메인 페이지</a>
  ```

#### Variable routing

- **주소 자체를 변수처럼 사용해서 동적으로 주소**를 만드는 것

  ```python
  path('hello/<str:name>/', views.hello)
  ```

  - default : str이고 int형으로도 가능
  - default 값은 생략 가능

- views.py에서 request 뒤에 두번째 인자로 변수가 들어옴

  ```python
  def hello(request, name):
      context = {
          'name': name
      }
      return render(request, 'hello.html', context)
  ```

## Framework의 성격

- Opinionated(독선적)
  - 자기만의 올바른 방법을 가지고 있음
  - 빠른 해결책을 준다. 문서가 잘 되어있고 강제성이 있음
  - But 개발자의 자유도가 떨어짐
- Unopinionated관용적
  - 개발자의 자유도가 크다
  - But 개발자의 손이 많이 간다.
- django → 다소 독선적 !

<br>

<br>

`03.10`

## Model

- 웹 어플리케이션의 데이터를 구조화하고 조작하기 위한 도구
  - database보다 조금 더 큰 개념
- 단일한 데이터에 대한 정보를 가짐
- 저장된 데이터베이스의 구조(layout)
  - **model과 database는 다른 거임!**
- django는 model을 통해 데이터에 접속하고 관리
- 일반적으로 각각의 model은 하나의 데이터베이스 테이블에 매핑

#### Database

- 체계화된 데이터의 모임

#### Query(쿼리)

- 데이터를 조회하기 위한 명령어
- 조건에 맞는 데이터를 추출하거나 조작하는 명령어

## Database의 기본구조

#### 1. 스키마(schema)

- 데이터베이스의 구조와 제약조건(자료구조, 표현 방법, 관계)에 관련된 전반적인 명세를 기술

#### 2. 테이블(table)

- 열(컬럼/필드)과 행(레코드/값)의 모델을 사용해 조직된 데이터 요소들의 집합
- 엑셀의 sheet 한개와 같음
- 필드(field) / 컬럼(column) / 속성
- 레코드(record) / 행(row) / 튜플

#### 3. 열(Column), 컬럼

- 각 열에는 고유한 데이터 형식이 지정됨
  - integer, text, null 등

#### 4. 행(row), 레코드

- 테이블의 데이터가 저장되는 부분

#### 5. PK(기본키)

- 각 행의 고유값, Primary Key
- **반드시 설정**해야하고 데이터베이스 관리 및 관계 설정시 주요하게 활용

<br>

## ORM(Object-Relational-Mapping)

- 객체 지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템(Django - SQL)간의 데이터를 변환하는 프로그래밍 기술(객체-관계-Mapping)
- 다른 시스템을 가진 데이터베이스를 조작
  - 우리는 파이썬(oop언어)을 계속 쓰고 이를 SQL로 해석해서 보내줌
  - 반대로 SQL 언어를 oop로 바꾸어서 줌

- 사용하는 이유 : 서로 다른 시스템간의 호환성을 위해 ORM을 사용
  - point : 우리는 python을 사용한다!(python의 object 활용)
- 장점
  - SQL 조작하지 않고 사용하던 oop언어로 DB를 조작할 수 있다.
  - SQL 의 절차적 접근이 아닌 객체 지향적 접근으로 인한 **높은 생산성**
    - 현대 웹 프레임워크의 요점은 **웹 개발의 속도를 높이는 것(생산성)**
- 단점
  - ORM만으로 완전한 서비스를 구현하기 어려운 경우가 있음
    - 필요할 때 SQL을 사용

<br>

## Migrations

- django가 model에 생긴 변화를 반영하는 방법(필드 추가, 모델 삭제 등)
- 참고 : https://docs.djangoproject.com/en/3.1/ref/models/fields/ (django model field)

- 명령어

  - makemigrations - 중요!!
    - model을 변경한 것에 기반한 새로운 migration(설계도)을 만들 때 사용
    - 각각 하나하나의 설계도 : migration
  - migrate - 중요!!
    - 데이터베이스에 적용시키는 것
    - ORM을 통해 DB로 보내는 것
    - migration을 DB에 반영하기 위해 사용
    - 설계도를 실제 DB에 반영하는 과정
    - 모델에서의 변경 사항들과 DB의 스키마가 동기화를 이룸
    - 하기 전에는 DB는 비어있음

  - sqlmigrate - 서브 커맨드(필요하면 사용)
    - 어떻게 동작할지 미리 확인할 수 있음
  - showmigrationgs - 서브 커맨드(필요하면 사용)
    - migration 과정이 어떻게 진행되었는지를 확인
    - migration 파일들이 migrate가 됐는지 안됐는지 여부 확인
      - X : 체크표시

<br>

#### 반드시 기억(이러한 사이클로 돌아간다)

1. models.py
   - model 변경사항 발생
2. python manage.py makemigrations
   - migration 파일 생성
3. python manage.py migrate
   - DB 적용

<br>

## Database API

- DB와의 소통
  - ex) 작성자가 이광교인 모든 게시글을 조회해줘 - 이때 우리가 쓰는 것은 python But, python만으로는 소통이 안되기 때문에 ORM 사용 - 특수한 문법에 따라서 python을 사용

#### DB API

- DB를 조작하기위한 도구

  - DB 관련 extension : SQLite 설치

- Model을 만들면 django는 객체들을 만들고 읽고 수정하고 지울 수 있는 database-abstract API를 자동으로 만듦(database-access API라고도 함)

- django queryset api(구글링)

  - https://docs.djangoproject.com/en/3.1/ref/models/querysets/

- 문법(데이터베이스와 소통하기 위한)

  `Article.objects.all()`

  Class Name, Manager, QuerySet API를 뜻함 all() : 핵심 method

  ex) all() : 데이터 전체를 조회하는 queryset

  - manager
    - django 모델에 데이터베이스 query작업이 제공되는 인터페이스
    - 기본적으로 DB를 조작하기 위한 명령어들을 들고 있어서 model과 QuerySet API 간의 인터페이스 역할을 함
    - model 뒤쪽에 object가 무조건 붙는다고 생각
  - QuerySet
    - 데이터베이스로부터 전달받은 객체 목록
    - 안의 객체는 0개, 1개, 여러개일 수 있음
    - 데이스베이스로부터 조회, 필터, 정렬 등을 수행 가능

  <br>

#### 데이터 저장

- 방법1

```python
article = Article()
    article.title = title
  	article.content = content
    article.save()
```

![image-20210310140732842](django.assets/image-20210310140732842.png)

![image-20210310140821803](django.assets/image-20210310140821803.png)

- 방법2

```python
title = request.GET.get('title')
content = request.GET.get('content')
article = Article(title=title, content=content)
article.save()
```

![image-20210310140925363](django.assets/image-20210310140925363.png)

![image-20210310140948120](django.assets/image-20210310140948120.png)

  - 방법3

  ```python
Article.objects.create(title=title, content=content)
  ```

  ![image-20210310141635193](django.assets/image-20210310141635193.png)

  ...: 부분 : 오타

  ![image-20210310141829056](django.assets/image-20210310141829056.png)

  - 조회(id대신 pk 쓰는 것을 권장!)

  ![image-20210310141736209](django.assets/image-20210310141736209.png)

<br>

:memo: shell_plus

> - django의 기본 shell 기능이 많이 없어서 설치해준다.
>
>   1. django extensions (구글검색)
>
>      - ```shell
>        pip install django-extensions
>        ```
>
>   2. installing - configuration (설치 후 등록 과정)
>
>      - ```python
>        INSTALLED_APPS = (
>            ...
>            'django_extensions',  # 이부분 추가
>        )
>        ```
>
>      - 할 때마다 settings에 추가 해주어야함!!
>
> - pip install ipython
>
> - 두개 설치 후에 `python manage.py shell_plus`로 사용 가능

<br>

## CRUD

- 대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말
  - ex) all() : Read의 역할
    - all()로 받았을때 : `<QuerySet []>` 리스트처럼 조작 가능

#### READ

- 어떻게 원하는 조건으로 잘 가져올 것인지가 중요!
- 2가지 분류
  - Methods that return new querysets   ex) all
  - Methods that do not return querysets   ex) get
- 대표적인 조회역할을 하는 QuerySet Method
  - all()
  - get()
    - 객체가 없으면 DoesNotExist 에러 발생
    - 객체가 여러개일 경우 MultipleObjectsReturned 에러 발생
    - 위와 같은 특징을 가지고 있기 때문에 unique 혹은 NOT NULL 특징을 가지고 있는 경우에만 사용 가능( → pk를 조회할 때 사용한다)
  - filter()
    - 우리한테 QuerySet을 return하는 method
    - 데이터가 하나일수도, 두개일수도(조회에 해당되는 만큼) 있음
- 조회를 할 때, 
  - 없는 pk 조회시 에러 발생 
  - 같은 content가 있을 때 그 content를 조회하면 에러가 발생
  - 즉, .get을 사용할때는 pk로만 조회

#### Field lookups

- 조회 시 특정 조건을 적용시키기 위해 사용
- 참고 : https://docs.djangoproject.com/en/3.1/topics/db/queries/ (making queries)
- QuerySet Method(get, filter, exclude)에 대한 키워드 인수로 사용

<br>

- 삭제된 pk값은 이용안함

<br>

## Admin site

- 사용자가 아닌 서버의 관리자가 활용하기 위한 페이지

- 참고 : https://docs.djangoproject.com/en/3.1/ref/contrib/admin/ (django admin site)

- Article class를 admin.py에 등록하고 관리

  - django.contrib.auth 모듈에서 제공

- record 생성 여부 확인에 유용하며 직접 record를 삽입할 수도 있음

- 관리자 만들기

  ```shell
  python manage.py createsuperuser
  Username : 입력
  Email : option이기 때문에 enter로 넘어갈 수 있음
  Password : 커서는 움직이지 않지만 입력되고 있는 것!!
  ```

  - SQLITE EXPLRER - auth_user를 가면 볼 수 있음(장고 기본 내장 앱의 table - 처음 migrate할 때 만들어진 것)

<br>

`03.12`

## Project

### Virual Environment

- 파이썬 인터프리터(파이썬 프로그램) : 내 컴퓨터 어디에서든지(전역) 파이썬 명령어를 치면 찾을 수 있게 해줌  

  - 환경변수 편집에서 설정 했었음(python.exe한테 파이썬 파일을 실행해달라고 터미널로 입력해주는 것), 

- 라이브러리 및 스크립트가 "시스템 파이썬"(운영체제 일부로 설치되어 있는 것)에 설치된 모든 라이브러리와 격리 되어있는 파이썬 환경

- 각 가상 환경은 고유한 파이썬 환경을 가지며 독립적으로 설치된 패키지 집합을 가짐

  - 가상환경 : 복제본 - 파이썬 프로그램을 복제하여 이 영역에 두는 것
  - 가상환경 지원 시스템 : venv, virtualenv, conda, pyenv 우리는 venv를 쓸 거임
    - 파이썬 3.3부터 venv가 기본 모듈로 저장
  - 가상환경 사용 이유
    - 라이브러리 관리가 쉽기 때문
    - 같이 프로젝트를 진행할 때 버전에 따라 라이브러리 등이 다를 수 있어서
    - pip로 설치한 패키지들은 Lib/site-package
    - 그런데 여러 프로젝트를 진행하게 되면 프로젝트마다 다른 버전의 라이브러리가 필요할 수도 있는데 파이썬에서는 한 라아브러리에 대해 하나의 버전만 설치가 가능하다. 
    - 더불어 각 라이브러리나 모듈은 서로에 대한 의존성(dependency)이 다르기 때문에 알 수 없는 충돌이 발생하거나 다른 여러 문제를 이르킬 수 있다.

- 파이썬 프로그램한테 manage.py를 실행시키면서 일을 더 주는 것

- git bash는 Unix 명령어를 씀

  <br>

- ```shell
  $ python -m venv venv
  python.exe를 실행 시켜줘 -m 특정 모듈을 실행시켜줘 venv : 모듈 // venv : 이름
  ```

  - 여기서 m은 modual의 약자, git에서 m은 message의 약자

- python38이 전역이면 venv는 지역

- ```shell
  $ source venv/Scripts/activate
  이후에 pip list를 치면 2가지 밖에 안나옴(기본적인 라이브러리)
  필요한 것들을 설치하면서 진행해야함
  source : scripts 파일을 실행시켜달라는거
  ```

- 이렇게 만들면 독립된 형태가 됨

- 항상 장고 프로젝트를 하면 venv(가상환경설정)를 하고 할거임

- git으로 관리하지 않을 것들

  - .gitignore(gitignore.io - python, windows, django, VisualStudioCode)

- ```shell
  $ django-admin startproject crud .
  ```

- 우리가 어떤 pip list를 썼는지 알려줘야함

  - pip freeze
    - 모든 라이브러리의 이름과 버전을 출력해줌
  - 참고
    - https://pip.pypa.io/en/stable/

- 필수요소들을 알려주는 파일을 만들거임

  - pip freeze > requirements.tx
    - 왼쪽의 실행 결과물을 오른쪽에 넣어달라는 명령어

- requirements에 있는 라이브러리를 설치하는 방법
  - pip install -r requirements.txt
    - -r : requirements(요구사항) - 뒤에 있는 것에 해당하는 것을 설치

- README.md
  
  - python이 몇 버전인지 적어줌 // 라이브러리는 requirements에 적어줌

<br>

- movies.json
  - model : movies.movie : 앱. 클래스

<br>

- 다 끝나고 git을 통해서 pair에게 보낼거임
- DB를 왔다갔다하게 되면 각자 만든 data에 따라 충돌하기 때문에
- fixture
  - 데이터의 모음으로 파일에 저장(json형식)하여 이것을 불러올거임
- django admin dumpdata를 이용할 거임
  - python manage.py dumpdata movies.movie 으로 data를 뽑고 이것을 파일에 저장하여 보내준다. (movies : 앱 이름, movie : 모델 이름(소문자로) --> articles.article)
  - python manage.py dumpdata --indent 4 movies.movie
    - 정렬해서 나옴
  - 저장할 때는 python manage.py dumpdata --indent 4 movies.movie > movies.json
- 불러와서 저장하는 법
  - movies - fixtures 폴더 추가해서 movies.json 파일을 넣어서 보내주고
    - fixtures 폴더 경로를 돌아보면서 찾음(templates와 같음)
  - 받아서 python manage.py migrate
  - fixtures 안에 movies를 만들고 movies.json을 넣음
  - python manage.py loaddata movies/movies.json
- 참고
  - models.py를 번역(makemigrations)하고 migration을 적용(migrate)을 해줌
  - migrate : 비어있는 표를 그려줌(schema만 생성)
  - loaddata : 표의 형식에 맞춰서 저장
- db.sqlite를 지웠다면 migrate부터 다시 해주어야함(db 초기화)
- model을 수정하는 경우에 구조가 바뀐것이기 때문에 makemigrations 부터 해야함

:heavy_check_mark: 순서

> - models.py(schema 구조선언) - migrations - (번역본) -  migrate(표를 그리기) - dumpdata(데이터 받고) - loaddata(넣어주기)
>   - dumpdata와 migrate 순서는 확실하지않음 두개 반대일수도...

- 그래서 가장 중요한 것이 modeling !!
  - 어떤 데이터를 저장할지 고민을 해야함
  - 데이터 관계

- created 시간과 같은 경우는 같은 데이터라도 시간의 차이로 값이 다르다
- 결론 db.sqlite는 git으로 관리를 안할거임!!

<br>

`03.15`

#### Project Tip

- 발표를 해야하는 프로젝트에서 보이는 데이터는 최대한 의미있게, 있어보이게 작성
  - ㅁㄴㅇㄹ, asdf 이런것들 x

<br>

`03.17`

### Form

- django 프로젝트의 주요 유효성 검사 도구들 중 하나이며, 공격 및 우연한 데이터 손상에 대한 중요한 방어수단
- 처리해주는 부분
  - 렌더링을 위한 데이터 준비 및 재구성
  - 데이터에 대한  HTML forms 생성
  - 클라이언트로부터 받은 데이터 수신 및 처리

#### Form Class

- djangor Form 관리 시스템의 핵심
- form내 field, field 배치, 디스플레이 widget, label 초기값, 유효하지 않는 field에 관련된 에러메세지를 결정
- django는 사용자의 데이터를 받을 때 해야 할 과중한 작업(데이터 유효성 검증, 필요시 입력된 데이터 검증 결과 재출력, 유효한 데이터에 대해 요구되는 동작 수행 등) 과 반복 코드를 줄여줌

#### Ouuting forms as HTML

- as_p : 각 필드가 단락(paragraph)으로 렌더링
- as_ul : 각 필드가 목록항목(list item)으로 렌더링
- as_table : 각 필드가 테이블 행으로 렌더링

#### Django의 2가지 HTML input 요소 표현 방법

- Form fields
  - input에 대한 유효성 검사 로직을 처리하며 템플릿에서 직접 사용됨
- Widgets
  - 웹 페이지의 HTML input 요소 렌더링 및 제출(submitted)된 원시 데이터 추출을 처리
  - 반드시 form fields에 할당되며 독자적으로 사용할 수 없다.
  - 유효성 검사 처리를 하지 않으면 form 필드에 귀속되어 사용
  - HTML 렌더링을 처리, 웹페이지에서 input element의 단순 raw한 렌더링 처리

<br>

### ModelForm Class

- model을 통해 Form Class를 만들 수 있는 Helper
- 일반 Form Class 와 완전히 같은 방식(객체 생성)으로 view에서 사용 가능
- Meta Class in ModelForm
  - Model의 정보를 작성하는 곳
  - 해당 model에 정의한 field 정보를 Form에 적용하기 위함
  - Model 케이스에 대한 정보를 작성하는 곳, 등록의 개념

<br>

### Form & ModelForm

- 뭐가 더 좋은 지가 아니라 역할이 다른 것! 서로 목적이 다르다
- djangoproject에서 ModelForm과 Form 비교 후에 대응되는 Form field를 사용해야한다.

#### Form

- 어떤 model에 저장해야 하는지 알 수 없으므로 유효성 검사 이후 cleaned_data 딕셔너리를 생성
- cleaned_data 딕셔너리에서 데이터를 가져온 후 .save() 호출해야함
- Form은 바로 저장 불가(어떤 레코드를 만들어야하는지 모름)
- model에 연관되지 않은 데이터를 받을 때 사용

#### ModelForm

- django가 해당 model에서 양식에 필요한 대부분의 정보를 이미 정의
- 어떤 레코드를 만들어야 할 지 알고 있으므로 바로 .save 호출 가능

- 모델에 연관되지 않는 데이터를 처리하기 위해 사용 form
- 모델에서 필요한 양식의 데이터라면 ModelForm사용
- 받고 검증하고 바로 저장 가능(레코드를 알고 있기 때문)

<br>

- db에 저장할 데이터가 아니라면 form 쓰고, 저장할 데이터라면 modelform 쓴다고 생각
- DB에 저장하는게 훨씬더 편리하게 하기 위해서 ModelForm 쓰는 것
- 사용자에게 폼으로 제공되어야 하지만 db에는 저장될 필요가 없는 데이터는 회원가입시 password 확인(Form을 사용하는 경우)

#### views.create 작성

- 정상적인 흐름이면 else 구문부터 작성이 되어야함!(흐름상), 외우는 것보다 이해

<br>

### create.html, update.html 수정

- django forms - Working with form templates - Rendering fields manually

  - ex) form.title, form.content로 분할 가능

- class 씌우기 여러가지 방법

- ```shell
  $ pip install django-bootstrap-v5
  ```

  - django bootstrap 5 검색 https://pypi.org/project/django-bootstrap-v5/
  - 설치! requirements.txt에 추가
  - bootstrap 5를 load를 하면 bootstrap에 있는 tag, filter 등을 사용 가능하게 함

- https://django-bootstrap-v5.readthedocs.io/en/latest/quickstart.html 여기서 cdn 추가

  - 기존 cdn 지우고 css와 javascript에 각각 넣어줌, 맨 위에 load bootstrap5

### extends - include tag

- template 상속
- 유지 보수를 위해서 사용
  - base.html의 코드가 많아지면 유지 보수의 목적이 희석됨
  - 새로운 template을 만듬(nav.html)
  - {% include 'nav.html' %}를 base.html의 body 부분에 넣어줌
  - include로 구조화를 시킴! (프로젝트에 따라서), 모듈 단위로 관리

### View decorators

#### decorator(데코레이터, @)

- 어떤 함수에 기능을 추가하고 싶을 때, 해당 함수를 수정하지 않고 기능을 연장 해주는 함수
- django는 다양한 기능을 지원하기 위해 view 함수에 적용할 수 있는 여러 데코레이터를 제공

#### Allowed HTTP methods

- 요청 메서드에 따라 view 함수에 대한 엑세스를 제한

- 요청이 조건을 충족시키지 못하면 HttpRestponseNotAllowed을 return

- require_http_methods(), require_POST(), require_safe() 

  -  require_safe() : require_GET() 대신에 대체로 씀

- https://docs.djangoproject.com/en/3.1/topics/http/decorators/

  - ```python
    from django.views.decorators.http import require_http_methods
    ```

#### postman

- 다시보기를 통해 다운
- API 개발을 할 때 사용하는 도구 - method를 자유롭게 변경해서 요청

:heavy_check_mark: check

> - 터미널을 종료해라 : 휴지통 모양을 눌러서 종료
> - 위젯을 사용할 때는 Meta 데이터 위에 쓴다! 들여쓰기, 닫는 태그 주의!
> - django form field에서 검색하여 사용 가능
> - http 상태코드 검색하면 오류 내용을 알 수 있음
>   - 2가 붙으면 일단 코드는 실행됐다는 것

<br>

`03.18`

### Static / Media

`03.19`

## Project

## RESIZE

Ctrl shift r : 강력 새로고침(캐시를 지우고 불러옴)

- width="100%"를 주면

  ex) 고해상도 : 가로가 1000픽셀인 상황에서 5000픽셀을 불러온다

  ex) 저해상도 : 화질이 낮은 것을 늘려서 깨진다

### django imagekit 사용

- https://pypi.org/project/django-imagekit/
- 다른 라이브러리를 사용해도 됨(여러가지 라이브러리 중 하나)

#### 1. Installation

- pillow 설치
- `pip install django-imagekit`
- settiings 설정

#### 2. Models

1) imageSpecField

- source : 무엇을 기준으로 썸네일을 만들지, 원본 데이터를 의미

- processors : 가로와 세로에 맞춰서 짤라주는 것(처리 방식)
- format : 확장자
- options : 품질, 올려서 고품질도 가능

2) ProcessedImageField

- 완성된 결과물을 저장해줌
- 처음에 올라갈때부터 수정돼서 올라감
- upload_to : 어느폴더에 올릴지 설정하는 곳(바꿀 수 있음)
- avatar로 했다면 이 폴더안에 image가 저장되어있음
  - RESIZE된 이미지가 저장되어있음
- 만약에 동접자 수가 많고 많은 이미지들이 올라온다면, 문제가 생겨서 어제 이미지들을 가져와야한다면?
  - upload_to='images/%Y/%m/%d/'로 바꾸어서 이미지를 효율적으로 관리
- 사용자별로 이미지를 관리해야한다면?
  - 사용자 개념을 배우고 추가적으로 학습 !!
- from imagekit.processors import ResizeToFill
  - 여백, 배경 등을 바꿔줄 수 있음
  - 검색해서 사용

#### 3. html 설정

1) imageSpecField

- image_thumnail.url
  - 썸네일을 보고 싶은 상황에서만 만들어주는 것
  - 원본 데이터를 가져와서 RESIZE
  - 그 상황마다 처리하기 때문에 DB에 저장되지 않음
    - makemigrations 작업을 안해도 됨
- ex) media - CACHE - image - 8k - 크롭된(200x200) image를 따로 저장(썸네일이미지)

- 디테일에서는 원본, 메인에서는 thumnail 이미지를 보여줌

2) ProcessedImageField

- 처리하고 완성된 결과물을 저장
  - DB에 저장이 되므로 makemigrations 필요

<br>

`03.22`

## Authentication

- 인증
- 자신이 누구라고 주장하는 사람의 신원을 확인하는 것

## Authorization

- 권한, 허가
- 가고 싶은 곳으로 가도록 혹은 원하는 정보를 얻도록 허용하는 과정

## Django Authentication System

- 인증과 권한 부여를 함께 저공하며, django에서는 이러한 기능이 어느정도 결합되어 있기 때문에 일반적으로 authentication system(인증시스템)이라고 함
- **User object, Web request 대한 인증 시스템**

<br>

### Authentication Built-in Forms

- django는 기본적으로 인증에 관련된 Built-in Form을 제공
- 회원가입, 로그인 등
- <br>

### :heavy_check_mark: 메모

- 인증에 관련된 앱의 이름은 보통 accounts를 사용한다.
- 참고
  - GET 방식으로 보내게 되면 id와 pw가 주소창에 노출이 됨
  - POST 방식으로 보내게 된다고 해서 브라우저에서 확인을 못하는 것이 아니라 개발자 도구를 통해서 확인이 가능 - 아예 숨길수 있는 것이 아님 (Network - login/ - Form Data에서 볼 수 있음)
- 단어 더블 클릭 후 ctrl + D 하면 같은 단어가 연속적을 잡힘 - 이후 수정 

<br>

### Web request

- django는 세션과 미들웨어를 사용하여 인증 시스템을 request 객체에 연결(**이미 연결아 되어 있음**)
- 이를 통해 사용자를 나타내는 모든 요청에 request.user를 제공(바로 사용 가능)
- 현재 사용자가 로그인하지 않은 경우 AnonymousUser 클래스의 인스턴스로 설정되며, 그렇지 않으면 User 클래스의 인스턴스로 설정됨

#### 로그인

- Session(이하 세션)을 Create하는 로직과 같음
- login() - 함수 제공
  - 현재 세션에 연결하려는 인증된 사용자가 있는 경우 login() 함수로 로그인 진행
  - request 객체와 User 객체를 통해 로그인 진행
  - Django의 session framework를 통해 사용자의 ID를 세션에 저장

#### 로그아웃

- 세션을 Delete하는 로직과 같음(ex. 세션이 만료 되었습니다)
- logout()
  - request 객체를 받으며 return이 없음(User객체는 받지 않음)
  - 현재 요청에 대한 **DB의 세션 데이터를 삭제**하고 **클라이언트 쿠키에서도 sessionid를 삭제** , **둘 다 삭제!**

#### HTTP (HyperText Transfer Protocol)

- HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜(규칙, 약속)
- 웹에서 이루어지는 모든 데이터 교환의 기초
- 클라이언트 - 서버 프로토콜
- 요청(request)
  - 클라이언트(브라우저)에 의해 전송되는 메시지
- 응답(responses)
  - 서버에서 응답으로 전송되는 메세지
- 특징
  - 비연결지향(connectionless) 
    - 서버는 응답 후 접속을 끊음
    - ex. naver에서 메인 페이지를 보여주고 서버를 계속 열어두는 것이 아니라 연결을 끊음
  - 무상태(stateless)
    - 접속이 끊어지면 클라이언트와 서버 간의 통신이 끝나며 상태를 저장하지 않음
    - 상태를 저장하지 않기 때문에 움직이면 로그인이 풀려야 하지만 로그인이 풀리지 않음 → 쿠키를 통해 로그인 상태 정보를 받음

#### Cookie(쿠키)

- 서버가 사용자의 웹 브라우저에 전송하는 작은 데이터 조각
- 브라우저(클라이언트)는 전송 받은 쿠키를 로컬에 key-value의 데이터 형식으로 저장
  - 동일한 서버에 재 요청 시 저장된 쿠키를 함께 전송(매번 보냄)
- 웹 페이지에 접속하면 요청한 웹 페이지를 받으며 쿠키를 로컬에 저장하고 클라이언트가 재요청시마다 웹 페이지 요청과 함께 쿠키 값도 같이 전송

#### Cookie(쿠키) 사용 목적

- **세션 관리**
  - 로그인, 아이디 자동완성, 공지 하루 안보기, 팝업 체크, 장바구니 등의 정보 관리
- 개인화
  - 사용자 선호, 테마 등의 세팅
- 트래킹
  - 사용자 행동을 기록 및 분석하는 용도

최근에는 privacy때문에 개인화와 트래킹에 대한 선택권을 우리한테 줌

#### Session(세션)

- 사이트와 특정 브라우저 사이의 stats(상태)를 유지시키는 것
- 클라이언트가 서버에 접속하면 서버가 특정 session id를 발급하고 클라이언트는 session id를 쿠키를 사용해 저장, 클라이언트가 다시 서버에 접속할 때 해당 쿠키(session id가 저장된)를 이용해 서버에 session id를 전달
- Django는 특정 session id를 포함하는 쿠키를 사용해서 각각의 브라우저와 사이트가 연결된 세션을 알아냄 (세션 정보는 django DB의 django_session 테이블에 저장)
- 주로 로그인 상태 유지에 사용

#### Cookie lifetime (라이프 타임, 일생)

##### 1. Session cookie

- 현재 세션(current session)이 종료되면 삭제
- 브라우저는 현재 세션이 종료되는 시기를 정의
- 일부 브라우저는 다시 시작할 때 세션(session restoring)을 사용해 계속 지속될 수 있도록 함

##### 2. Permanent cookie

- Expires 속성에 지정된 날짜 혹은 Max_Age 속성에 지정된 기간이 지나면 삭제

##### 검사 - Application의 Cookies 안에서 볼 수 있음

- 해당되는 쿠키를 지우고 새로고침을 하면 장바구니가 사라진다.(ex. sid 쿠키 삭제)

### 로그인 사용자에 대한 접근 제한

#### 1. is_authenticated attribute

- User class의 속성
- 사용자가 인증되었는지 확인하는 방법
- User에 항상 True이며 AnonymousUser에 대해서만 항상 False
- 단, 이것은 권한(permission)과는 관련이 없으며 사용자가 활성화 상태(active)이거나 유효한 세션(valid session)을 가지고 있는지도 확인하지 않음  → 로그인이 되어있는지 아닌지만 확인(T or F)

#### 2. login_required decorator

- 사용자가 로그인 했는지 확인하는 view를 위한 데코레이터
- 로그인 된 사용자의 경우 view 함수를 실행
- 로그인 하지 않은 사용자는 settings.LOGIN_URL에 설정된 경로로 redirect 시킴
  - LOGIN_URL의 기본 값은 '/accounts/login/'  → 인증 관련 앱을 accounts로 한 이유

<br>

### Signup

- https://docs.djangoproject.com/en/3.1/topics/auth/default/#module-django.contrib.auth.forms

### User

- django 인증 시스템의 핵심
- Users가 django 인증 시스템에서 표현되는 모델
- 일반적으로 사이트와 상호작용 하는 사람들을 나타냄
- django 인증 시스템에서는 오직 하나의 User Class만 존재
- AbstractUser Class의 상속을 받음
- **AbstractUser**
  - User model을 구현하는 완전한 기능을 갖춘 기본 클래스
  - https://github.com/django/django/blob/main/django/contrib/auth/forms.py - django github
  - https://docs.djangoproject.com/en/3.1/topics/auth/default/ - django authentication system
  - https://docs.djangoproject.com/en/3.1/topics/auth/customizing/ - django user model 
    - 어떠한 곳에서도 User를 직접 참조하지 않을 거임

<br>

`03.23`

### DELETE 차이점

- 권한

  ```python
  # 다른 유저도 delete 가능 --> 강력한 누군가가 다른사람을 탈퇴시킬 필요가 있을 때
  def delete(request, user_pk):
      user = get_user_model().objects.get(pk=user_pk)
      user.delete()
      return redirect('accounts:index')
  
  def delete(request):
      request.user.delete()
      return redirect('articles:index')
  ```

:memo: 참고

> - 문법에러 : 컴파일 에러
> - 문법은 틀린 것이 없는데 실행과정에서 에러가 뜨는 것 : 런타임 에러(화면에 노란창)
> - user model을 customizing할 것이기 때문에 User를 바로 쓰지 않고 get_user_model을 사용
> - crud - settings - MIDDLEWARE
>   - 거의 항상 작동해야하는 것을 따로 작성해놓은 것(request, csrf 등) - 미들웨어
>   - AuthenticationMiddleware 가 views에서 user를 쓸 수 있게함
> - crud - settings - TEMPLATES
>   - request가 request.user.is_authentication를 쓸 수 있게 함

<br>

<br>

`03.08`

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

`03.10`

## 보충수업

- RDB : Relational DB, SQL을 통해서 접근
- ORM - 다른 웹프레임워크에서도 많이 쓰임
- 모델링 정보를 추가, 수정, 삭제 등 변동이 일어났다.

  1. models.py 모델링 소스코드를 수정했다.

  2. makemigrations : models.py에 적힌 소스코드를 토대로 '설계도'를 만든다.
  3. migrate : 
- render : 현재 주소에서 그려주는 역할만

<br>

`03.15`

## 보충수업

#### 가상환경

- 기본적으로 pip list는 전역환경(global)에 깔려있는 것들이 나온다.

- ```shell
  $ python -m venv venv
  ```

  - 가상환경을 만듬

- ```python
  $ source venv/Scripts/activate
  ```

  - venv - Scripts - activate를 실행시켜야 됨
  - global환경에 영향을 끼치지않고 가상환경에서만 영향을 끼침

- 가상환경에서 나가는 명령어

  - ```python
    $ deactivate
    ```

- pyenv, virtualenv : 파이썬의 버전을 바꾸고 싶을 때 환경변수를 들어가는 것이 아니라 명령어 한줄로 해결해줌

- code . : 현재 폴더에서 vscode를 켜줌

- ```shell
  $ pip freeze > requirements.txt
  ```

  - 가상환경에서 설치해준 파일을 적어서 넘겨줘하기 때문에 설치된 파일이 만들어진 파일을 만듬

#### gitignore

- git으로 관리하지 않을 것들을 등록해준다.
- .gitignore로 만듬
- 파일안에 venv/ 이런식으로 써주면 status에서 venv가 사라짐
- 일반적으로 등록하지 않아도 되는 list가 정해져있고 이것들을 보는 곳이 gitignore.io
- 맨 처음에 세팅(add하기 전에)

#### venv한 파일을 받는 경우

- clone을 했지만 venv가 설치되어 있지않기 때문에 venv를 설치한다.

- 프로젝트에 필요한 것들을 설치해주어야한다.

- ```shell
  $ pip install -r requirements.txt
  ```

  - 가상환경에 설치해준 라이브러리를 받음

- 추가적으로 필요한 것을 install 했다면 다시 만들어서 보내준다

  - ```shell
    $ pip freeze > requirements.txt
    ```

<br>

### 정리

| Method | URL                        | 의미                                    |
| ------ | -------------------------- | --------------------------------------- |
| GET    | `/articles/`               | 게시글 목록을 보여준다(`.html`, `JSON`) |
| GET    | `/articles/new/`           | 게시글 작성 페이지를 보여준다.(`.html`) |
| POST   | `/articles/create/`        | 사용자가 입력한 데이터를 DB에 저장한다. |
| POST   | `articles/글번호/delete/`  | 글 번호를 주고 DB에서 삭제한다.         |
| GET    | `/articles/글번호/edit/`   | 게시글 수정 페이지를 보여준다.          |
| POST   | `/articles/글번호/update/` | 수정한 데이터를 DB에서 바꿔준다.        |

- 읽어오기만 할 때는 GET, DB에 변동을 주는 것은 POST
- 게시글을 수정할 때
  - URL 2개 필요
    - 게시글을 수정할 수 있는 페이지
    - 수정한 데이터를 DB에서 바꿔주는 URL
- render / redirect
  - render : 현재페이지에서 '.html'을 브라우저 화면에 보여주는 것
  - redirect : 다른 주소로 요청을 보내주는 것(특정한 url로 가는 것)
- dumpdata / loaddata
  - dumpdata : 현재 DB의 상태를 파일로 만드는 것
  - loaddata : dump된 파일을 DB에 넣고 싶은 경우
  - 이 두개는 데이터 동기화를 위한 것이 아니라 시드 데이터(샘플 데이터)를 위한 명령어임
  - 여러 명의 개발자 서로 데이터를 동기화하기 위한 수단으로 사용하면 안됨!(망할 확률이 높음)
  - 데이터 동기화를 위해서는 My SQL, PostgreSQL 같은 설치형(서버형) RDB를 도입한다.

<br>

`03.17`

## Django Form

> 1. HTML 코드를 손쉽게 생성해준다.
> 2. 유효성 검사를 편하게 할 수 있다.
>    - `is_valid()` : 해당 field에 맞게 검사해줌    →    장고의 장점

<br>

#### 어플리케이션을 만들 때 고려해야 할 점

- 우리는 유저가 아니다 `you != user`

- 원하는 대로 해주지 않음
- ex) 핸드폰 번호 : 010 - 1234 -1234
  - label + input placeholder="핸드폰 번호는 010 - 0000 - 0000 형식으로 입력해주세요."
  - But 010 -12341234, 12341234 이런식으로 들어올 수 있음 - 이러한 부분을 생각해줘야함!

<br>

### 1. Form

> 직접 만든 Django Form
>
> model에 대한 정보가 없어서 form.save() 으로 바로 DB에 저장할 수 없다.
>
> DB에 저장하려는 데이터를 받은게 아니라면 ModelForm을 쓰면 안되고 Form을 사용해야 한다.

### 2. ModelForm

> class Meta : data의 data
>
> 만들어 놓은 모델을 알아서 form을 만들라고 하는 것(정보만 줌) : `model = Article`
>
> 어떤 필드를 장고 필드로 만들기 원하는지 알려줘야함 : `field = '__all__'`
>
> save() : ModelForm에 제공되는 method
>
> form.save()로 바로 DB에 저장

<hr>

:cherries: TIP

> - `django-admin startproject muyaho .` : 현재폴더에 생성

<br>

:heavy_check_mark: 써야하는 것

> - 요청 뒤에는 /(엔드 슬래시)
> - context 값은 dictionary로 넘어간다!
> - app 이름은 복수형으로! - 클래스와 혼동될 수 있기 때문에
> - app을 생성 후에 등록을 해야한다.
> - form은 반드시 action과 method를 쓰고 시작!
>   - method default는 GET이고 명시해주는 것이 좋음
> - label은 id값과 연결됨
> - a의 href, form의 action 안에 url을 쓸 때는 '/url_name/' 이런식으로!
> - from . import views 처럼 디렉토리를 명시해주는 것이 좋음

<br>

:checkered_flag: 스타일 가이드

> - {{ variable }} 괄호에 붙이지 않기 

<br>

`03.22`

# Django Auth

## Session

- Create : login
- Delete : logout
- 서버는 수백, 수천, 수만 개의 클라이언트와 동시에 통신을 해야한다.
- HTTP 프로토콜은 기본적으로 연결되어 있지 않고(Connectionless), 서로를 인식할 수 있는 상태 정보도 없다.(Stateless)

- 서버와 클라이언트는 상태정보를 기억하여 서로를 식별하게끔 만들 수 있다. → 세션을 유지하도록 만든다.

## Cookie

- **세션을 유지하는 방식** 중 가장 널리 사용되는 방식
- 서버가 사용자의 웹 브라우저에 전송하는 작은 데이터 조각(MDN)
- 브라우저는 데이터 조각들을 
- 검사 - Application
  - Domain 
    - 웹브라우저가 분석해서 보내줌
    - ex) 구글, 네이버, 유튜브 등에 있는 쿠키 전부를 가지고 있는 것이 아니라 네이버에 있으면 네이버 Domain의 쿠키만 가지고 있음
  - path : 서버 경로 뒤에 붙는 세부정보
  - Expires / Max-Age : 
- 쿠키는 위험한가?
  - 개인정보를 쿠키에 저장해서는 안된다.
  - django에서는 id, pw를 주는 것이 아니라 sessionid를 주고 자신도 가지고 있음(사용자 인식 수단), 실제 중요한 데이터는 DB에 있음 → 쿠키가 보안 위협을 받지 않도록

#### 쿠키의 종류('파기시점'의 유무로 구분)

- Session Cookie : 브라우저를 닫으면 삭제되는 쿠키
- Permanent(Persistent) Cookie : 브라우저를 닫거나 컴퓨터를 재시작해도 남아있는 쿠키(Expires & Max-Age)

## User

- Create : signup
- Update : update
- Delete : delete

## HTTP

- Connectionless
- Stateless

### :heavy_check_mark: 면접 질문 참고

> - session과 cookie 설명
> - django의 장점 → django session(Auth)
>
> > 추가적으로
> >
> > - Notion 이나 Github.io 활용해서 포트폴리오 만들어보기!



### WS

- **User 모델에 직접적으로 참조하지 않기!**
  - Customizing할 거라서 직접 참조 X
  - `get_user_model()`을 참조

```python
User = get_user_model()
users = User.objects.all()
context = {
    'users': users,
}
return render(request, 'accounts/index.html', context)
```



