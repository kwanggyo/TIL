# Git

1. 저장소(repository)만들기  - git이 관리하는 폴더(directory) // git은 폴더별로 관리 .git이 관리

   ```shell
   $ git init (폴더마다 한번씩)
   ```

   TIL 안에 new 폴더를 만들어도 git이 관리함(하위폴더이기때문)

   **mater 가 뒤에 있으면 init 하지말기**

   혹시 했으면 그 폴더안의 .git 삭제하기

   주의사항 : 이미 init한 repo에는 또 init 하지 않는다

2.  파일을 스테이징하기

   ```shell
   $ git add 파일명
   ```

3.  파일을 커밋하기

   ```shell
   $ git commit -m '커밋 메세지 내용(변경사항을 요약해서 적음)'
   ```

- 상태 확인하기

  ```shell
  $ git status
  ```

- 내가 누군지 정보 입력하기

  ```shell
  $ git config --global user.name 유저이름
  
  $ git config --global user.email
  ```

  처음에 설치할때 한번만

- 커밋 기록 확인하기

  ```shell
  $ git log --oneline(옵션)
  ```

<br>

## 원격(remote) 저장소

- github - 무료, 개인 개발자가 많이 씀(ms가 중간에 인수함 8조원 - 무료 기능이 확대됨)
- gitlab(SSAFY에서 사용중) - 유료, 회사, 조직에서 많이 씀

폴더(repository) 단위로 관리됨!

내 컴퓨터의 저장소 -> github의 내가 만든 원격 저장소

원격 저장소를 지정하는데 지정한 이름을 origin이라고 하겠다.

그 주소는 https://github.com/kwanggyo/TIL.git 다.

```shell
$ git remote add origin https://github.com/kwanggyo/TIL.git
```



```shell
$ git push origin master
```



발표 자료형 ppt 초안을 만들 때,

발표전까지 자료가 제대로 도착하지 않았을 경우? - 낫자료ppt

제대로 도착했을 때? - 퍼펙자료ppt

이런 식으로 분기해서 관리하는 것 : 브랜치

final 프로젝트 전까지는 다루지 않을 예정



- 처음에 git init을 하면 기본적으로 이름이 master라고 정해짐



수정 - add commit push

if 내컴퓨터 format?

원격 저장소 repo 컴퓨터로 다운!

```shell
$ git clone 저장소주소
```

shift insert로 붙여넣기



```shell
$pwd
```

터미널을 어디서 열었는지 알 수 있음

users/다음에 띄어쓰기나 한글 있으면 안됨

<br>

## 과제 제출할 때

```python
git init(초기 한번만, 이미 master가 떠있는지 아닌지 확인)
git remote add origin 주소
git add .
git commit -m '메세지'
git push origin master
```

<br>

## 협업할 때

1. git clone A
2. git remote add myorigin B
3. git push myorigin master