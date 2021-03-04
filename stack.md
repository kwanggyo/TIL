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

<br>

:heavy_check_mark: 백트래킹과 깊이우선탐색(DFS)의 차이

> - 어떤 노드에서 출발하는 경로가 해결책으로 이어질 것 같지 않으면 더 이상 그 경로를 따라가지 않음으로써 시도를 줄임(Prunning 가지치기)
> - 깊이우선탐색 : 모든 경로 추척  //  백트래킹 : 불필요한 경로를 조기에 차단
> - 백트래킹 알고리즘을 적용하면 일반적으로 경우의 수가 줄어들지만 이 역시 최악의 경우에는 여전히 지수함수 시간을 요한다.

- 백트래킹 알고리즘 절차
  1. 상태 공간 트리의 깊이 우선 검색을 실시
  2. 각 노드가 유망한지를 점검
  3. 만일 그 노드가 유망하지 않으면, 그 노드의 부모 노드로 돌아가서 검색을 계속

