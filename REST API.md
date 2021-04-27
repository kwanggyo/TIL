# REST API

# `04.26`

## API(Application Programming Interface)

- 프로그래밍 언어가 제공하는 기능을 수행할 수 있게 만든 인터페이스
  - 어플리케이션과 프로그래밍으로 소통하는 방법을 말한다.

- CLI, GUI는 각각 명령줄(git bash)과 그래픽(아이콘)을 통해서 특정 기능을 수행하는 것이며  API는 프로그래밍을 통해 그 일을 수행할 수 있다.

- `Client`가 `Server`로 요청을 보내면 응답으로 비디오, 문서, 이미지, 어플리케이션 등을 준다.
- 지금까지는 응답으로 HTML을 주는 것이었다면 이제는 JSON파일을 받아서 여러 디바이스에서 활용! → 프로그래밍을 통한 요청에 JSON을 응답하는 서버를 만드는 것이 목표 !

### Web API

> - 웹 어플리케이션 개발에서 다른 서비스에 요청을 보내고 응답을 받기 위해 정의된 명세
> - 현재 웹 개발은 추가로 직접 모든 것을 개발하지 않고 여러 Open API를 가져와서 활용하는 추세
>   - 구글, 카카오 지도 API, 우편번호, 도로명, 지번, 검색 API 등

<br>

## REST(REpresentational State Transfer)

- 웹 설계 상의 장점을 최대한 활용할 수 있는 아키텍쳐 방법론

- 네트워크 아키텍쳐 원리의 모음

  1. 자원을 정의(data 정의)
  2. 자원에 대한 주소를 지정하는 방법

- REST 원리를 따르는 시스템 혹은 AP를 RESTful API라고 하기도 함

  → `자원`과 `주소`를 저장하는 방법

- URI, HTTP method, Representations로 구성된다.

### 1. URI(자원)

> - Uniform Resource Identifier
> - 통합 자원 식별자
> - 인터넷의 자원을 나타내는 유일한 주소
> - 인터넷에서 자원을 식별하거나 이름을 지정하는 데 사용되는 간단한 문자열
> - URL을 포함하고 있는 상위 개념
> - 하위 개념으로 URL, URN이 있다.
>   - 크게 URL과 URN으로 나눌 수 있지만 URN을 사용하는 비중이 적기 때문에 일반적으로 URL은 URI를 통칭하는 말로 사용하기도 한다.
>   - 모든 URL → URI, 모든 URI !→ URL
>   - URL(Uniform Resource Locator)
>     - 네트워크 상에 자원(리소스)이 어디 있는지(주소)를 알려주기 위한 약속
>     - 자원을 HTML 페이지, CSS 문서, 이미지 등이 될 수 있음
>     - '웹 주소' 또는 '링크'라고도 불림
>   - URN(Uniform Resource Name)
>     - 자원의 인식표(자원의 주민등록증)
>     - URL과 달리 상대적인 위치에 영향을 받지 않고 유일한 이름 역할을 함(독립적 이름)
>     - 자원의 이름이 변하지 않는 한 자원의 위치를 이곳저곳 옮겨도 문제없이 동작
>       - ex) ISBN(국제표준도서번호), ISBN 0-486-27557-4 : 로미오와 줄리엣
>     - 우리가 직접 작성하는 경우는 거의 없다.
>   - URL과 URN 비교 예시
>     - 서울시 강남구 테헤란로 멀티캠퍼스 → URL
>     - 만약 멀티캠퍼스가 새로운 곳으로 이사 가게 된다면,
>       - 더이상 '서울시 강남구 테헤란로 멀티캠퍼스'라는 주소(URL)로 멀티캠퍼스는 찾을 수 없다.
>       - 새로운 주소(URL) '대전광역시 유성구 멀티캠퍼스'로 찾아야한다.
>       - 하지만 멀티캠퍼스가 다른 곳으로 가더라도 URN을 통해 멀티캠퍼스 라는 것을 식별 가능 → 멀티캠퍼스라는 고유한 이름(URN)은 변함이 없다.
>     - URN은 자원의 ID를 정의하고, URL은 자원을 찾는 방법을 제공한다.
>     - 둘은 상호 보완적인 관계를 갖는다.
>
> #### URI 구조
>
> > - `Scheme /Protocol` : http
> > - `Host` : localhost(IP주소가 들어갈 수 있음)
> > - `Port` : 3000(장고는 일반적으로 8000 사용)
> > - `Path` : posts/3 : 자원의 경로
> > - `Query` : q=http(?뒤에 붙음, key-value 형태) - 웹 서버에 제공하는 추가적인 파라미터, &로 연결 가능
> > - `fragment` : #containers - 해당 자원 안에서의 북마크 역할을 함(해당 문서의 특정 부분을 보여줌), 서버로 보내는 요청이 아니라 브라우저에 알려주는 것(브라우저가 특정 위치를 인식하기 위한 것)
>
> #### 설계 주의사항
>
> > - 밑줄(_)이 아닌 하이픈(-)을 사용
> >   - URI의 가독성을 위해
> > - 소문자 사용
> >   - 대소문자에 따라 다른 자원으로 인식하게 됨
> > - 파일 확장자는 포함시키지 않음
> >   - naver.com/index.html→ index.html을 포함하지 않고 사용한다. naver.com

### 2. HTTP Method(행위)

> #### HTTP(HyperText Transfer Portocol)
>
> > - HTML 문서와 같은 자원들을 가져올 수 있도록 해주는 프로토콜(규칙, 약속)
> > - 웹에서 이루어지는 모든 데이터 교환의 기초
> > - 클라이언트가 요청을 보내고 서버가 응답을 줌(클라이언트 - 서버 프로토콜)
> > - 요청(requests)
> >   - 클라이언트(브라우저)에 의해 전송되는 메세지
> > - 응답(response)
> >   - 서버에서 응답으로 전송되는 메세지
>
> #### HTTP 특징
>
> > - 비연결 지향(connectionless)
> >   - 서버는 응답 후 접속을 끊는다.
> > - 무상태(stateless)
> >   - 접속이 끊어지면 클라이언트와 서버 간의 통신이 끝나면 상태를 저장하지 않는다.
> >   - 쿠키와 세션으로 보완한다.
>
> #### HTTP Method
>
> > - 자원에 대한 행위의 역할을 한다.
> > - 즉, HTTP는 HTTP Method를 정의하여 주어진 자원에 수행하길 원하는 행동을 나타낸다.
> >   - ex) 문서를 줘, 글을 삭제해줘, 글을 수정해줘 등
> >   - GET, POST 등의 행동
> > - 의미론적으로 행위를 규정하기 때문에 '실제 그 행위 자체가 수행됨'을 보장하진 않는다.
> >   - GET → 무조건 문서를 줄거라는 행위를 보장하지 않음
> > - HTTP verb 라고도 함
>
> #### HTTP Method 종류
>
> > - GET
> >   - 특정 자원의 표시를 요청하며, 오직 데이터를 받기만 한다.
> > - POST
> >   - 서버로 데이터를 전송하며, 서버에 변경사항을 만든다.
> >   - 이제는 수정할 때 PUT으로 보낼거임
> > - PUT
> >   - 요청한 주소의 자원을 수정한다.
> > - DELETE
> >   - 지정한 자원을 삭제한다.
> > - 행위에 대한 규정을 Method로 한다.
> >   - naver.com 같은 url이 아니라 GET, PUT 등
> >   - ex) GET : 작성하는 문서를 주는 것, POST : 글을 작성 → 이때 url(articles)은 같다.

### 3. Representation(표현)

> #### JSON(JavaScript Object Notation)
>
> > - 가벼운 데이터 포맷(lightweight data-interchange format)
> > - 자바스크립트 객체 문법을 따르며, 구조화된 데이터를 표현하기 위한 문자 기반 데이터 포맷
> > - 일반적으로 웹 어플리케이션에서 클라이언트로 데이터를 전송할 때 사용
> > - 자바 스크립트 구문에 기반을 두고 있지만 차이점이 있으니 주의 !
>
> #### JSON 특징
>
> > - 사람이 읽고 쓰기 쉽고 기계가 파싱(해석&분석)하고 만들어 내기 쉽다.
> >
> >   - 파이썬을 dictionary, 자바스크립트의 object처럼 C계열의 언어가 갖고 있는 자료구조로 쉽게 변환할 수 있는 key-value의 구조로 되어있다.
> >
> > - 자바스크립트가 아니어도 JSON을 읽고 쓸 수 있는 기능이 다양한 프로그래밍 언어 환경에서 지원된다.
> >
> > - 기본적으로 문자열로 되어있는데 이를 우리가 쓸 수 있는 JSON으로 바꿔주는 작업을 Parsing(파싱)이라고 한다. → JSON으로 바꾸는 과정(파이썬에서는 dictionary로 바꾸는 과정)
> >
> >   - 문자열 → JSON 객체 : Parsing
> >   - JSON 객체 → 문자열 : Stringification
> >
> >   ```python
> >   import requests
> >   
> >   URL = '<http://naver.com/helllo/Hi/>...중략..json'
> >   response = requests.get(URL)
> >   
> >   # Dictionary로 Parsing
> >   data = response.json()
> >   
> >   # <class 'dict'>
> >   print(type(data))
> >   ```

<br>

## RESTful

### REST

> - URI는 정보의 자원을 표현해야 한다.
> - 자원에 대한 (어떠한)행위는 HTTP Method로 표현한다.

### RESTful하게 작성 되었는가? - 예제

> 틀린 것이 아니라 조금 부족하다 정도?
>
> - GET/articles/1/read/ → X, URI에 불필요한 정보(행위 표현)가 포함 : read
>
> - GET/articles/1/delete/ → X, URI는 자원에 대한 행위는 HTTP method로 표현
>
>   → DELETE/articles/1/ 이러한 식으로 작성해줘야 한다.

<br>

## DRF(Django REST Framework)

- Web API 구축을 위한 강력한 toolkit을 제공
- REST framework 개발에 필요한 다양한 기능을 제공

### Serialization(직렬화)

> - 중간 변환기 역할을 한다.
>
> - 데이터 구조나 객체 상태를 동일하거나 다른 컴퓨터 환경에 저장하고 나중에 재구성할 수 있는 포맷으로 변환하는 과정이다.
>
> - 예를 들어 DRF의 Serializer는Django의 Queryset 및 Model Instance와 같은 복잡한 데이터를, JSON, XML 등의 유형으로 쉽게 변환할 수 있는 Python 데이터 타입으로 만들어 준다.
>
> - DRF의 Serializer는 Django의 Form 및 ModleForm 클래스와 매우 유사하게 작동
>
> - articles → serialization(언어마다 바꿔주는 타입이 다름) → json
>
>   ```python
>   # seed 문법
>   
>   더미데이터를 필요할때 장고시드를 쓰면 좀 더 빨리 작업이 가능하다.
>   물론 나중에는 우리가 쓰는 데이터로 바꿔야한다.
>   
>   $ python manage.py seed articles --number=20
>   
>   articles : 앱 이름
>   number : 보여질 개수
>   ```
>
> - Django와 비교
>
>   - Response
>     - Django : HTML  
>     - DRF : JSON
>   - Model
>     - Django : ModelForm
>     - DRF : ModelSerializer
>
> - 참고문서
>
>   - https://docs.djangoproject.com/en/3.2/topics/serialization/
>   - https://www.django-rest-framework.org/tutorial/2-requests-and-responses/

<br>

<br>

# `04.27`

## :memo: Django 순서

> 1. python -m venv venv : 가상환경 설치
>
> 2. source venv/Scripts/activate : 가상환경 활성화
>
> 3. pip install django : 장고 설치
>
> 4. django-admin —version : 3.2가 뜨는데 상관없음(최근에 3.1에서 3.2로 바뀜)
>
> 5. django-admin startproject api . : 현재 폴더에 프로젝트 생성
>
> 6. pip install django-seed djangorestframework django-extensions ipython 
>
>    : extensions, ipython은 shell plus를 쓰기 위한 것
>
>    - shell plus : 라인을 한줄씩 접근해서 데이터를 뽑아내기 좋은 인터페이스
>
> 7. settings.py의 INSTALLED_APPS에 'django_seed', 'django_extensions', 'rest_framwork', 추가
>
> 8. python manage.py startapp articles : 앱 생성, 후 등록
>
> 9. urls.py → models.py → serializers.py
>
> 10. makemigrations, migrate : model을 생성하면 해준다 !
>
> 11. python manage.py seed articles --number=20
>
>     : articles - model의 database에 랜덤한 20개의 값을 넣어줌
>
>     - makemigrations, migrate 이후에 해야한다!
>
>     - python manage.py shell_plus ------------------------------- 여기부터는 shell을 이용해서 값을 확인
>
>       1. Article.objects.all() : 20개가 출력되는지 확인
>
>          : 여기서는 serializer를 확인해볼거임
>
>       2. from articles.serializers import ArticleSerializer
>
>       3. serializer = ArticleSerializer()
>
>       4. serializer : 어떻게 생겼는지 나옴
>
>          read_only=True : 수정할 수 있는 타입이 아니다.
>
>       5. article = Article.objects.get(pk=1)
>
>       6. article
>
>       7. serializer = ArticleSerializer(article)
>
>       8. serializer
>
>       9. serializer.data
>
>          {'id': 1, 'title': 'Ask create manager create follow model such.'}
>
>          : 모델인스턴스인 article이 dict형태로 변환되었다는 것을 보기 위해서 진행한 것
>
>       10. type(serializer.data)
>
>           rest_framework.utils.serializer_helpers.ReturnDict
>
>           : dict은 아님
>
>       11. serializer.data.get('id')
>
>           1

<br>

## :heavy_check_mark: 참고

> - API서버가 RESTful하다는 것은 이사람이 만든 서버를 다른 사람도 잘 이해할 수 있다.
>
> - 가이드일 뿐 무조건 지켜야하는 것은 아니고 적당히 알아볼 수 있게(규약) 만들면 된다.
>
>   - ex) url은 자원만을 나타내고 동작은 포함하지 않는다.
>
> - crud에 해당하는 동작을 get, post, put, delete를 통해 구현한다.
>
> - serializer 역할
>
>   - model instance를 우리가 사용하기 좋게끔 바꿔준다.
>   - 유효성 검사를 해준다.
>   - 사용시 url은 건들지 않고 방법만 바꿔준다.
>
> - Djaongo를 통해서 값을 넣어줄 때(Django DRF Form)
>
>   ```python
>   {
>       "title": "hello world",
>       "content": "good bye"
>   }
>   ```
>
>   - 큰 따옴표, 반점 주의 ! 이렇게 쓰지 않으면 에러 발생
>
> - PUT과 PATCH 차이
>
>   - PUT : 수정을 하더라도 기존의 내용을 똑같이 입력해서 보내줘야한다.
>     - ex) PUT(title, content)
>   - PATCH : title만 보내줘도 나머지값은 알아서 이전값을 사용한다.
>
> - Django / 에 관하여..
>
>   - 장고에서 /가 포함되지않는 데이터를 받게되면 /를 붙여서 redirect를 한다. → GET 방식 
>   - 즉, DELETE에서 /를 안붙이고 하면 /를 붙여서 보내는데 GET방식이기 때문에 동작하지 않는다
>
> - Serializer class 부분
>
>   - commentSerializer에서 article, content 두가지 모두 다 받으면 둘다 검사를 한다.
>
>     - 에러가 발생할 수 있기 때문에 serializers.py 에서 read_only 옵션을 통해 해결 !
>     - ex) article_title = serializers.CharField(source='article.title', read_only=True)
>
>   - serializer 클래스에서 만든 필드는 read_only_fields(Meta부분)에는 못넣는다 !
>
>     Meta 위에서 넣어야한다 !

<br>

### Postman

> - 다운 : https://www.postman.com/downloads/
> - 사용법
>   - 회원, 비회원 둘 다 사용 가능
>   - Workspace - MyWorkspace
>   - request를 생성해서 url을 넣어주고 원하는 방식을 설정
>     - ex) http://127.0.0.1:8000/api/v1/articles/
>   - Body의 form-data에서 값 입력
>   - send를 통해서 결과를 확인
>   - body - raw - text를 json으로 바꾸고 텍스트로 써도 된다. {"text" ...

<br>

### Swagger → 이런게 있다 정도,,

> #### mtv - 최종결과 : 화면 → 일반 사용자를 타겟
>
> > UI에서 사용법이 어느정도 드러남
>
> #### json 데이터 - api 서버 : 프로그램을 위한 데이터를 제공
>
> >  json데이터는 어떻게 쓰는 부분인지 명시해 놓아야 쓸 수 있다.
> >
> > ex) 서버에서 article을 조회하려면? comment를 조회하려면?
> >
> > ​	api/v1/comments/GET 우리는 개발자니까 알고 있지만 사람들은 모르기 때문에 알려줘야한다.
> >
> > 이런걸 정의해 놓은 것을 api 문서(Documents)라고 한다.
> >
> > → 우리가 서버를 만들면 이러한 문서를 만들 필요가 있다
> >
> > 직접 다 만들 수 있지만 우리 서버를 통해서 만들어 주는 녀석이 있음 → Swagger
> >
> > pip install drf-yasg 설치 후 INSTALLED_APPS에 'drf_yasg'
> >
> > app 밑에 있는 urls.py에 작성할거임
> >
> > 지금 만드는 것은 어렵다.. 이런게 있구나정도?

### 댓글 추가할 때

> #### CREATE 하는 방법 2가지
>
> 1. articles/4/comments
> 2. comments / POST

<br>

<br>