# 알고리즘

: 유한한 단계를 통해 문제를 해결하기 위한 절차나 방법

<br>

``02.08``

## 시간 복잡도

- 시간복잡도는 문제의 크기가 커짐에 따라 시간에 얼마나 증가하는지 근사적으로 표기하는 방법
- 보통 n은 문제의 크기를 나타냄.

<br>

## 문제 풀이

- ```python
  # 연산자 : 컴퓨터한테 일을 시킬 때 가장 작은 단위
  # 자료형 : 메모리, 값의 범위, 어떤 계산이 가능한지 등 중요!
  # 수식(expression) = 연산자 + 피연산자
  # 실행문(명령문, statement)
   	# if, for, while (제어문, 실행흐름을 제어)
  ```

<br>


:memo: 알고리즘 설계기법

> - 완전 탐색
> - 백트래킹
> - 동적계획법
> - 분할 정복
> - 탐욕

<br>

:memo: 알고리즘 문제 유형

> 1. 결정 문제(decision problem)
>    - True or False로 답하는 문제
> 2. 최적화 문제(optimization problem)
>    - 후보해(가능한 방법)들 중에서 최적해를 찾는 문제
>    - 최적해 : 문제의 조건에 해당하는 값이 최소 또는 최대가 되는 경우

<br>

:memo: 디버그

> - 파이참에 있는 Debug 활용
> - breaking point를 잘 잡고 실행!
>   - Step over : 함수를 들어가지 않음
>   - Step into : 함수를 들어감
>   - Step out : 함수를 진행하다가 빠져 나옴
>   - resume : 다음 breakpoint로 이동

<br>

### 좋은 알고리즘

- 정확성
- 작업량
- 메모리 사용량
- 단순석
- 최적화

<br>

``02.09``

### 버블 정렬(Bubble Sort)

- 인접한 두 개의 원소를 비교하며 자리를 계속 교환하는 방식

- 시간복잡도 : O(n^2)

<br>

### 카운팅 정렬(Counting Sort)

- 항목들의 순서를 결정하기 위해 집합에 각 항목이 몇 개씩 있는지 세는 작업을 하며, 선형 시간에 정렬하는 효율적인 알고리즘
- 제한사항
  - 정수나 정수로 표현할 수 있는 자료이어야 한다.
  - 카운트를 위한 충분한 공간 할당을 위해 집합 내 가장 큰 정수를 알아야 한다.
- 시간복잡도 : O(n)

<br>

``02.15``

### 이차 배열

- 입력 방법

  ```python
  N, M = map(int, input().split())
  arr = []
  # 첫번째
  for i in range(N):
      arr.append(list(map(int, input().split())))
      
  # 두번째
  arr = [0] * N
  for i in range(N):
  	arr[i] = list(map(int, input().split()))
      
  # 세번째
  arr = [list(map(int, input().split())) for _ in range(N)]
  ```

#### 행 우선 순회

- ```python
  for i in range(len(array)):
      for j in range(len(array[0])):
          array[i][j]
  ```

#### 열 우선 순회

- ```python
  for i in range(len(array[0])):
      for j in range(len(array)):
          array[i][j]
  ```

#### 지그재그 순회

- ```python
  for i in range(len(array)):
      for j in range(len(array[0])):
          array[i][j + (M-1 - 2*J)*(J % 2)]
  ```

<br>

### 델타를 이용한 2차원 탐색

: 2차 배열의 한 좌표에서 4방향의 인접 배열 요소를 탐색하는 방법

- ```python
  arr[0...n-1][0...n-1]
  dr = [-1, 1, 0, 0]
  dc = [0, 0, -1, 1]
  # drc = [[-1, 0], [1, 0], [0, -1], [0, 1]]
  r = 1
  c = 1
  for i in range(4):
      nr = r + dr[i]
      nc = c + dc[i]
      print(arr[i][j])
  ```

<br>

------------ 부분 집합 정리 필요 --------------

``02.16``

:memo: 메모리를 정해두는 이유

> - 메모리를 정해두지 않아서 그때 그때 다르면 컴퓨터는 식별을 해야한다.
> - 이러한 경우 빠르게 일처리를 하기 위해서 메모리를 정해둔다.



:heavy_check_mark: break와 return을 언제 써야 하는지 생각!!

> - break는 바로 위의 for문을 빠져나옴
> - 돌고 있는 전체 for문을 빠져나오고 싶으면 함수를 만들어서 return 사용!

