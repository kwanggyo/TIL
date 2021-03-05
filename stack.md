## Stack

- 자료를 쌓아 올린 형태의 자료 구조
- 스택에 저장된 자료는 선형구조를 갖는다.
- 자료를 삽입하거나 꺼낼 수 있다.
- 마지막에 삽입한 자료를 먼저 꺼내는 후입선출(LIFO : Last-In-First-Out)
  - 삽입 : push
  - 삭제 : pop
  - 스택이 공백인지 아닌지 확인 : isEmpty
  - 스택의 top에 있는 item(원소)을 반환 : peek
- 스택에서 마지막에 삽입된 원소의 위치를 top이라고 한다.

<br>

- 스택 구현시 고려 사항
  - 장점 : 1차원 배열을 사용하여 구현할 경우 구현이 용이하다.
  - 단점 :  스택의 크기를 변경하기 어렵다.
- 해결 방법
  - 저장소를 동적으로 할당하여 스택을 구현하는 방법
    - 구현이 복잡하지만 메모리를 효율적으로 사용한다.

<br>

:heavy_check_mark: 선형 / 비선형 구조

> - 선형 : 자료 간의 관계가 1대1의 관계
> - 비선형 : 자료 간의 관계가 1대N의 관계 (ex. 트리)

<br>

## 재귀호출

- 자기 자신을 호출하여 순환 수행되는 것
- 재귀호출방식을 사용하면 함수를 만들면 프로그램의 크기를 줄이고 간단하게 작성 가능

- ex. factorial, Fibonacci

- 문제점 : 엄청난 중복 호출이 존재할 수 있다.

  ```python
  def Fibonacci(N):
      if N < 2:
          return N
      else:
          return Fibonacci(N - 1) + Fibonacci(N - 2)
  
  print(Fibonacci(35))
  ```

  

<br>

## Memoization

- 컴퓨터 프로그램을 실행할 때 이전에 계산한 값을 메모리에 저장해서 매번 다시 계산하지 않도록 하여 전체적인 실행속도를 빠르게 하는 기술

  ```python
  def MemoozationFibo(n):
      global memo
      if n >= 2 and len(memo) <= n:
          memo.append(MemoozationFibo(n - 1) + MemoozationFibo(n - 2))
      return memo[n]
  
  memo = [0, 1]
  
  print(MemoozationFibo(35))
  ```

<br>

## DP(Dynamic Programming)

- 그리디 알고리즘과 같이 최적화 문제를 해결하는 알고리즘

- 먼저 입력 크기가 작은 부분 문제들을 모두 해결한 후에 그 해들을 이용하여 보다 큰 크기의 부분 문제들을 하결하고, 최종적으로 원래 주어진 입력의 문제를 해결하는 알고리즘

- 적용 방법

  1. 문제를 부분 문제로 분할

  2. 가장 작은 부분 문제부터 해를 구함

  3. 결과를 테이블에 저장하고, 테이블에 저장된 부분 문제의 해를 이용하여 상위 문제의 해를 구함

  ```python
  def DP_fibo(n):
      f = [0, 1]
  
      for i in range(2, n + 1):
          f.append(f[i-1] + f[i - 2])
      return f[n]
  
  print(DP_fibo(35))
  ```

- DP의 구현 방식

  - recursive : MemoizationFibo
  - iterative : DP_fibo

- memoization을 재귀적 구조에 사용하는 것보다 반복적 구조로 DP를 구현한 것이 성능면에서 효율적

- 재귀적 구조는 내부에 시스템 호출 스택을 사용하는 오버헤드가 발생

<br>

## DFS(Depth First Search) : 깊이우선탐색

- 비선형 구조인 그래프는 그래프로 표현된 모든 자료를 빠짐없이 검색하는 것이 중요함

- 한 방향으로 갈 수 있는 경로가 있는 곳까지 깊이 탐색해 가다가 더 이상 갈 곳이 없으면, 가장 마지막에 만났던 갈림길 간선이 있는 정점으로 돌아와서 다른 방향으로  반복 탐색하여 모든 정점을 방문하는 순회 방법

- 후입선출 구조의 스택 사용

- 알고리즘

  1. 시작 정점 v를 결정하여 방문

  2. 정점 v에 인접한 정점 중에서
     - 방문하지 않은 정점 w가 있으면, 정점 v를 스택에 push하고 정점 w를 방문, 그리고 w를 v로 하여 다시 2를 반복
     - 방문하지 않은 정점이 없으면, 탐색의 방향을 바꾸기 위해서 스택을 pop하여 가장 마지막 방문 정점을 v로 하여 다시 2를 반복
  3. 스택이 공백이 될 때까지 2를 반복

  ```python
  # 정점수, 간선수 (V, E)
  # 7 8
  # 1 2 1 3 2 4 2 5 4 6 5 6 6 7 3 7
  
  def dfs(v):
      S = [v]
      visited[v] = 1
      print(v, end='-')
  
      while S:
          for w in G[v]:
              if visited[w] == 0:
                  S.append(w)
                  visited[w] = 1
                  print(w, end='-')
                  v = w
                  break
          else:
              v = S.pop()
  
  # 인접 행렬로 받아오기
  V, E = map(int, input().split())
  G = [[] for _ in range(V + 1)]  # 그래프
  visited = [0] * (V + 1)  # 방문정보
  arr = list(map(int, input().split()))
  
  for i in range(0, E * 2, 2):
      u = arr[i]
      v = arr[i + 1]
      G[u].append(v)
      G[v].append(u)  # 무향이므로
  
  print(G)  # 인접 리스트
  ## [[], [2, 3], [1, 4, 5], [1, 7], [2, 6], [2, 6], [4, 5, 7], [6, 3]]
  
  dfs(1) # 탐색 경로
  ## 1-2-4-6-5-7-3-
  ```



## 계산기

- 중위 표기법(infix notation)
  - 연산자를 피연산자의 가운데 표기하는 방법
  - ex) A + B
- 후위 표기법(postfix notation)
  - 연산자를 피연산자 뒤에 표기하는 방법
  - AB+

<br>

## 백트래킹

- 해를 찾는 도중에 '막히면' (해가 아니면) 되돌아가서 다시 해를 찾아 가는 기법
- 최적화(optimization) 문제와 결정(decision) 문제를 해결할 수 있음
- ex) 미로 찾기, n-Queen, Map coloring, 부분 집합의 합
- 어떤 노드의 유망성을 점검한 후에 유망(promising)하지 않다고 결정되면 그 노드의 부모로 되돌아가(backtracking) 다음 자식 노드로 감
- 가지치기(Prunning) : 유망하지 않는 노드가 포함되는 경로는 더 이상 고려하지 않는다.
- 완전탐색을 하는 것이고 가지치기를 통해 효율적인 완전 탐색을 한다.

<br>

:heavy_check_mark: 백트래킹과 깊이우선탐색(DFS)의 차이

> - 어떤 노드에서 출발하는 경로가 해결책으로 이어질 것 같지 않으면 더 이상 그 경로를 따라가지 않음으로써 시도를 줄임(Prunning 가지치기)
> - 깊이우선탐색 : 모든 경로 추척  //  백트래킹 : 불필요한 경로를 조기에 차단
> - 백트래킹 알고리즘을 적용하면 일반적으로 경우의 수가 줄어들지만 이 역시 최악의 경우에는 여전히 지수함수 시간을 요한다.

- 백트래킹 알고리즘 절차
  1. 상태 공간 트리의 깊이 우선 검색을 실시
  2. 각 노드가 유망한지를 점검
  3. 만일 그 노드가 유망하지 않으면, 그 노드의 부모 노드로 돌아가서 검색을 계속

<br>

## 순열

- 비트

  ```python
  arr = [1, 2, 3]
  
  N = 3
  
  sel = [0] * N  # 뽑은 결과를 적음
  
  # check 10진수 정수
  def perm(idx, check):
      if idx == N:
          print(sel)
          return
  
      for j in range(N):
          # j번째 원소를 활용을 했군. 그럼 쓰면 안되지.
          if check & (1 << j): continue
  
          sel[idx] = arr[j]
          perm(idx+1, check | (1<<j))  # 일회성으로 사용해서 원상복구가 필요 없다.
  
  perm(0, 0)
  
  ##
  [1, 2, 3]
  [1, 3, 2]
  [2, 1, 3]
  [2, 3, 1]
  [3, 1, 2]
  [3, 2, 1]
  ```

- 재귀

  ```python
  arr = [1, 2, 3]
  
  N = 3  # len(arr)
  
  sel = [0] * N  # 결과들이 저장될 리스트
  check = [0] * N  # 해당 원소를 이미 사용했는지 안했는지에 대한 체크
  
  
  def perm(idx):
      # 다 뽑아서 정리했다면
      if idx == N:
          print(sel)  # 결과를 출력z`
      else:
          for i in range(N):
              if check[i] == 0:  # 해당 원소가 아직 사용 안된 상태
                  sel[idx] = arr[i]  # 값을 써라
                  check[i] = 1  # 사용을 했다는 표시
                  perm(idx + 1)
                  check[i] = 0  # 다음 반복문을 위한 원상복구
  
  perm(0)
  
  ##
  [1, 2, 3]
  [1, 3, 2]
  [2, 1, 3]
  [2, 3, 1]
  [3, 1, 2]
  [3, 2, 1]
  ```

- 스왑

  ```python
  arr = [1, 2, 3]
  
  N = 3
  def perm(idx):
      if idx == N:
          print(arr)
  
      else:
          for i in range(idx, N):
              # 순서를 바꾸고
              arr[idx], arr[i] = arr[i], arr[idx]
              # 원상복귀
              perm(idx + 1)
              arr[idx], arr[i] = arr[i], arr[idx]
  
  perm(0)
  
  ##
  [1, 2, 3]
  [1, 3, 2]
  [2, 1, 3]
  [2, 3, 1]
  [3, 2, 1]
  [3, 1, 2]
  ```

  

- 예제

  - 순열 개수

  ```python
  N = 3
  
  cnt = 0
  def func(idx):
      if idx == N:
          global cnt
          cnt += 1
      else:
          for i in range(N - idx):
              func(idx + 1)
  
  func(0)
  print(cnt)
  ## 6
  ```

  - 중첩 포함

  ```python
  N = 3
  arr = 'ABC'
  order = [0] * N  # 생성한 순열을 저장
  
  # for i in range(N):  # 첫번째 위치의 요소(or 인덱스)를 선택
  #     order[0] = arr[i]
  #
  #     for j in range(N):  # 두번째 위치의 요소를 선택
  #         order[1] = arr[j]
  #
  #         for k in range(N):  # 세번째 위치의 요소를 선택
  #             order[2] = arr[k]
  #
  #             print(*order)
  
  # ===========================================================================
  def perm(idx):      # idx = 함수호출의 깊이, for문의 중첩횟수, 몇개를 선택했는지(선택한 요소의 수)
      if idx == N:    # 모든 선택이 끝났다. 함수호출트리의 마지막단에 왔다. 더이상 고를 필요가 없다.
          print(*order)
      else:
          for i in range(N):
              order[idx] = arr[i]
              perm(idx + 1)
  perm(0)
  
  ##
  A A A
  A A B
  A A C
  A B A
  A B B
  A B C
  A C A
  A C B
  A C C
  B A A
  B A B
  B A C
  B B A
  B B B
  B B C
  B C A
  B C B
  B C C
  C A A
  C A B
  C A C
  C B A
  C B B
  C B C
  C C A
  C C B
  C C C
  ```

  - for문으로 구현(중첩 x)

  ```python
  N = 3
  arr = 'ABC'
  order = [0] * N  # 생성한 순열을 저장
  
  for i in range(N):  # 첫번째 위치의 요소를 선택
      if arr[i] in order: continue  # list에 in을 쓰는 것은 좋지 않은 방법! 시간이 오래걸림, 비효율적
      order[0] = arr[i]
  
      for j in range(N):  # 두번째 위치의 요소를 선택
          if arr[j] in order: continue
          order[1] = arr[j]
  
          for k in range(N):  # 세번째 위치의 요소를 선택
              if arr[k] in order: continue
              order[2] = arr[k]
  
              print(*order)
  
              order[2] = ''  # 여기서 두번째 for문으로 돌아갈 때 k에서 선택했던 것을 지우고 감
          order[1] = ''
      order[0] = ''
  
  # ===========================================================================
  # # 함수로 구현
  # def perm(idx):  # idx = 함수호출의 깊이, for문의 중첩횟수, 몇개를 선택했는지(선택한 요소의 수)
  #     if idx == N:  # 모든 선택이 끝났다. 함수호출트리의 마지막단에 왔다. 더이상 고를 필요가 없다.
  #         print(*order)
  #     else:
  #         for i in range(N):
  #             if arr[i] in order: continue
  #             order[idx] = arr[i]
  #             perm(idx + 1)
  #             order[idx] = ''
  # perm(0)
  
  ##
  A B C
  A C B
  B A C
  B C A
  C A B
  C B A
  ```

  - visited로 구현

  ```python
  N = 3
  arr = 'ABC'
  order = [0] * N  # 생성한 순열을 저장
  visited = [0] * N  # 중복 체크
  
  # for i in range(N):
  #     if visited[i]: continue
  #     order[0] = arr[i]
  #     visited[i] = 1
  #
  #     for j in range(N):
  #         if visited[j]: continue
  #         order[1] = arr[j]
  #         visited[j] = 1
  #
  #         for k in range(N):
  #             if visited[k]: continue
  #             order[2] = arr[k]
  #             visited[k] = 1
  #             print(*order)
  #
  #             visited[k] = 0
  #         visited[j] = 0
  #     visited[i] = 0
  
  # ===========================================================================
  def perm(idx):
      if idx == N:
          print(*order)
  
      else:
          for i in range(N):
              if visited[i]: continue
              order[idx] = arr[i]
              visited[i] = 1
              perm(idx + 1)
              visited[i] = 0
  perm(0)
  
  ##
  A B C
  A C B
  B A C
  B C A
  C A B
  C B A
  ```

  - 매개변수 + Sum 으로 합 찾기

  ```python
  N = 3
  arr = [[2, 1, 2],
         [5, 8, 5],
         [7, 2, 2]]
  order = [0] * N    # 생성한 순열을 저장
  visited = [0] * N    # 중복 체크
  
  def perm(idx, cur_sum):
      if idx == N:
          S = 0
          for i in range(N):
              S  += arr[i][order[i]]
          print(S, cur_sum)
      else:
          for i in range(N):
              if visited[i]: continue
              visited[i] = 1
              order[idx] = i
              perm(idx + 1, cur_sum + arr[idx][i])
              visited[i] = 0
  
  perm(0, 0)
  
  ##
  12 12
  9 9
  8 8
  13 13
  9 9
  17 17
  ```

  - 매개변수만 사용하여 합 찾기

  ```python
  N = 3
  arr = [[2, 1, 2],
         [5, 8, 5],
         [7, 2, 2]]
  order = [0] * N    # 생성한 순열을 저장
  visited = [0] * N    # 중복 체크
  
  def perm(idx):
      if idx == N:
          S = 0
          for n in range(N):
              S += arr[n][order[n]]
          print(S)
      else:
          for i in range(N):
              if visited[i]: continue
              visited[i] = 1
              order[idx] = i
              perm(idx + 1)
              visited[i] = 0
  
  perm(0)
  
  ##
  12
  9
  8
  13
  9
  17
  ```

  - 매개변수로 최솟값 찾기 + 가지치기

  ```python
  N = 3
  arr = [[2, 1, 2],
         [5, 8, 5],
         [7, 2, 2]]
  order = [0] * N    # 생성한 순열을 저장
  visited = [0] * N    # 중복 체크
  
  def perm(idx, cur_sum):
      global ans
      if ans < cur_sum: return  # 가지치기!! 이미 최솟값을 가짐
  
      if idx == N:
          if ans > cur_sum:
              ans = cur_sum
      else:
          for i in range(N):
              visited[i] = 1
              perm(idx + 1, cur_sum + arr[idx][i])
              visited[0]
  
  ans = 987654321
  perm(0, 0)
  print(ans)
  
  ##
  8
  ```

<br>

## 분할 정복

- 분할(Divide) : 해결할 문제를 여러 개의 작은 부분으로 나눔
- 정복(Conquer) : 나눈 작은 문제를 각각 해결

- 시간복잡도 : O(log2n)

  ```python
  # for문 이용 -> O(n)
  
  def Iterative_Power(x, n):
      result = 1
  
      for i in range(1, n + 1):
          result *= x
  
      return result
  
  # 분할 정복을 이용한 거듭제곱 O(logn)
  def Recursive_Power(x, n):
      if n == 1: return x
      if n % 2 == 0:
          y = Recursive_Power(x, n // 2)
          return y * y
      else:
          y = Recursive_Power(x, (n-1) // 2)
          return y * y * x
  
  print(Iterative_Power(3, 5))
  print(Recursive_Power(3, 5))
  
  ##
  243
  243
  ```

<br>

## 퀵 정렬

- 주어진 배열을 두 개로 분할하고, 각각을 정렬
- 합병 정렬과 다른 점
  - 합병 정렬 : 그냥 두 부분으로 나눔
  - 퀵 정렬 : 분할할 때, 기준 아이템(pivot item) 중심으로 이보다 작은 것은 왼편, 큰 것은 오른편으로 위치시킴
  - 각 부분 정렬이 끝난 후 합병 정렬은 ''합병''이라는 후처리 작업이 필요, 퀵 정렬은 필요 X 

- 최악의 시간 복잡도 O(n^2), but 평균 복잡도 O(nlogn)