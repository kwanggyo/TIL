# Git

1. 저장소(repository)만들기  - git이 관리하는 폴더(directory) // git은 폴더별로 관리 .git이 관리

   ```shell
   $ git init (폴더마다 한번씩)
   ```

   TIL 안에 new 폴더를 만들어도 git이 관리함(하위폴더이기때문)

   **mater 가 뒤에 있으면 init 하지말기**

   혹시 했으면 그 폴더안의 .git 삭제하기

   주의사항 : `이미 init한 repo에는 또 init 하지 않는다!`

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

내 컴퓨터의 저장소 → github의 내가 만든 원격 저장소

원격 저장소를 지정하는데 지정한 이름을 origin이라고 하겠다.

그 주소는 https://github.com/kwanggyo/TIL.git 다.

```shell
$ git remote add origin https://github.com/kwanggyo/TIL.git
```

```shell
$ git push origin master
```

<br>

## Branch

발표 자료형 ppt 초안을 만들 때,

발표전까지 자료가 제대로 도착하지 않았을 경우? - 자료없는 ppt

제대로 도착했을 때? - 자료있는 ppt

이런 식으로 분기해서 관리하는 것 : 브랜치

final 프로젝트 전까지는 다루지 않을 예정

<br>

## :heavy_check_mark: 참고

- 처음에 git init을 하면 기본적으로 이름이 master라고 정해짐

- 수정 - add commit push

- if 내컴퓨터 format? → 원격 저장소 repo 컴퓨터로 다운!

```shell
$ git clone 저장소주소
```

> - shift insert로 붙여넣기

```shell
$pwd
```

> - 터미널을 어디서 열었는지 알 수 있음
> - users/다음에 띄어쓰기나 한글 있으면 안됨

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

<br>

<br>

## GIT UNDO

- 과거로 돌아가는 것
  - 안하는게 가장 좋은 방법

##### Working Directory

##### Staging Area

##### Repository

- `ls - a`찍으면 .git(숨겨진 파일)이 보임

- `rm -rf .git` : git 폴더를 지움

- `git log --oneline` : 커밋을 간단히 볼 수 있음

- git init → git add a.txt → `git rm --cached a. txt` : add한 것을 내림(rm은 remove의 약자)

- commit 취소 방법

  - commit message 수정 방법

  - `git commit --amend` : vim이 나옴
    - i를 누르면 입력모드가 됨, esc(끔)
    - 입력모드가 아닌상태에서 :wq 를 입력하고 enter를 치면 수정됨 (write quit)

    - 관심있으면 openvim을 들어가서 찾아보기

    - insert mode와 normal mode 이해정도 알면 좋음
    - vim : 마우스가 없는 환경에서도 명령어로 조작할 수 있게

  - commit을 했는데, 파일을 추가하고 싶은 경우

    - git add 추가하고 싶은 파일

<br>

<br>

## Git 협업 / 버전관리

- 이전 버전으로 돌아가기(최대한 안쓰기)
- git reset --hard/soft/(mixed) 8d72d6 (log --oneline에 있는 원하는 시점의 8e8d73와 같은 코드)
  - hard : 그 시점의 코드로 돌아감(add했던 기록까지 삭제 - add를 할 수 없는 상황)
  - soft : 과거로 돌아가지만 그 사이의 값을 들고 있음(add한 기록까지는 남김)
  - mixed(default) : add 전 단계까지 남아있음(add를 할지말지 결정)
- Woking Directory에 저장 --mixed
- Staging Area : --soft
- hard는 Working Directory 까지 고침

<br>

## GIT

- 버전관리
- 협업

### :heavy_check_mark: 참고

> -  웹 IDE : git push한 파일을 브라우저 내에서 수정하는 기능
> - 앞으로 여기서 수정 X
> - reset : commit 역사와 내용 전부 고침
> - revert : commit 역사는 남겨놓고 실제 내용만 고침 - 새로운 커밋을 만드는 것과 같아서 충돌을 방지
> - 둘 다 많이 쓰이는 방식은 아니지만 과거로 돌아가는 설정을 할 때 상황에 맞게 쓰기!
> - revert는 돌아갈려는 커밋시점의 파일 내용으로 수정하고 새로 커밋하는 거랑 차이가 없다
>
> <hr>
>
> - `rm -rf .git` : git init 지우기
>
> - `origin` : 원격 저장소 주소 의미
>
> - main이 되는 줄기를 master라고 하고 있음
>
> - 어느 위치에 있는지 표시해주는 거였음 (master) 부분
>
> - git 이라는 프로그램이 기본적으로 master라는 이름을 들고 있기 때문에 master를 사용했음
>
> - `git log --oneline - HEAD` :  내가 보고 있는 데이터를 의미
>
> - `switch`는 HEAD의 위치를 바꾸어줌
>
> - [guide github](https://guides.github.com/introduction/flow/)
>
> - 배포된 서비스가 master
>
>   - 여기서 수정하는 것은 실제 사용자가 쓰는 것을 수정하는 것임 - 어떤 문제가 발생할지 모름
>
>     → 수정할 때 브랜치에서 수정
>
> - 보통 이런식의 구성
>
>   - **master**
>   - hotfixes
>   - release branches
>   - **develop** : 모든 개발자가 다 반영해야 하는 것을 관리
>   - feature branches

<br>

## 병합 → main 줄기에서 merge를 해야한다 !

- 외부의 것을 내부로 가져오는 것

### master에 수정이 없었을 때

> - git switch master 합치고자 하는 것중에 더 메인인 것으로 (change는 brunch 이름을 말함)
> - git merge change 병합후
> - git branch -d change

### master에 수정이 있었을 때 (수정이 안겹칠때)

> - git switch master
> - git merge feature/login
> - git branch -d feature/login

### master에 수정이 있었을 때 (수정이 겹칠때 ex. 둘다 로그인 부분 수정)

> - git switch master
> - git merge feature/signup
> - 충돌이 일어남
> - 둘 중 하나를 선택 or 복수 선택 후
> - add, commit
> - git branch -d feature/signup
>
> - ex)
>   - account / article을 각각 만들 때
>   - settings.py -> develop으로 공통
>   - 각각 만들고 병합
> - git log --oneline --graph
>   - 초록색 : 로컬 저장소의 브랜치 이름
>   - 빨간색 :원격저장소의 브랜치(remote 저장소)
>   - 원격저장소에서 merge를 하지 않는 것이 좋음 로컬을 추천
>   - 어디가 최신인지 알 수 있어야함!

<br>

<br>

## Branch 설정

- clone 받을 때 폴더 이름을 바꾸고 싶으면 맨 뒤에 폴더이름 써주면 됨
  - git2라는 폴더 : `git clone 주소 ---.git git2`
- 브랜치 만들 때
  - `git branch kwang`
- 위치 바꿀 때
  - `git switch kwang`

<br>

## 협업 Merge

- 2명이 할 때 각자의 브랜치를 만듦
- 각자 브랜치로 switch 후에 작업하고 add, commit, push

### merge(gitlab에서)

> - **데이터 최신화는 그 브랜치에 가서 가져와야함**
> - **다른 브랜치에서 가져오려고 하면 합치려고 함**
> - Gitlab에서 merge할 때 충돌이 일어나면 로컬에서 수정하는 것이 좋음!
>
>   - 합치려고 한 부분을 pull 받아서 최신화한 후
>   - 합치고 하나만 선택할지 둘 다 선택할지 결정 후 add commit push
>
>   - 코드의 싱크 상태 확인 - A, B 둘 다 최신화된 데이터를 가지게 해준다.
>     - B에서 마지막 작업을 했으면  A에 가서 merge한 데이터를 pull 받는다.
>   - Gitlab에서 branch를 지웠어도 각자의 로컬에는 branch가 살아있음
> - merge request(gitlab) == pull request(github) 