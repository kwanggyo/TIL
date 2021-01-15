# Git

1. 저장소(repository)만들기  - git이 관리하는 폴더(directory) // git은 폴더별로 관리 .git이 관리

   ```python
   $ git init (폴더마다 한번씩)
   ```

   TIL 안에 new 폴더를 만들어도 git이 관리함(하위폴더이기때문)

   mater 가 뒤에 있으면 init 하지말기

   혹시 했으면 그 폴더안의 .git 삭제하기

   주의사항 : 이미 init한 repo에는 또 init 하지 않는다

2.  파일을 스테이징하기

   ````python
   $ git add 파일명
   ````

3.  파일을 커밋하기

   ```python
   $ git commit -m '커밋 메세지 내용(변경사항을 요약해서 적음)'
   ```

- 상태 확인하기

  ```python
  $ git status
  ```

- 내가 누군지 정보 입력하기

  ```python
  $ git config --global user.name 유저이름
  
  $ git config --global user.email
  ```

  처음에 설치할때 한번만

- 커밋 기록 확인하기

  ```python
  $ git log --oneline(옵션)
  ```