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

### 부분집합

- ```python
  # 예시
  arr = [3, 6, 7, 1, 5, 4]
  n = len(arr)
  for i in range(1<<n):
      for j in range(n):
          if i & (1<<j):
              # print(f'조건문 i, j값 : {i}, {j}')
              print(arr[j], end=' ')
      print()
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

<br>

:heavy_check_mark: break와 return을 언제 써야 하는지 생각!!

> - break는 바로 위의 for문을 빠져나옴
> - 돌고 있는 전체 for문을 빠져나오고 싶으면 함수를 만들어서 return 사용!

<br>

``02.17``

### 문자열

- chr() : 문자 → 아스키코드 (atoi)
- ord() : 아스키코드 → 문자 (itoa)

<br>

:heavy_check_mark: find, index

> - 찾는 것이 없을 때 find : -1, index : ValueError

<br>

:heavy_check_mark: ==, is

> - == : 값이 같은지
> - is : 주소값이 같은지

<br>

 ### 패턴 매칭

#### 1. 고지식한 패턴 검색(Brute Force)

- 처음부터 끝까지 차례대로 순회하면서 패턴 내의 문자들을 일일이 비교하는 방식

- O(MN)

- ```python
  # while문 사용
  M = len(p) # 찾을 패턴의 길이
  N = len(t) # 전체 텍스트의 길이
  
  # while문 활용
  def BruteForce(p, t):
      i = 0  # t의 인덱스
      j = 0  # p의 인덱스
      while j < M and i < N:
          if t[i] != p[j]:
              i = i - j
              j = - 1
          i = i + 1
          j = j + 1
      if j == M:
          return i - M  # 검색 성공
      else:
          return -1  # 검색 실패
      
  # for문 사용
  def BruteForce2(p,t):
      N = len(t)
      M = len(p)
  
      # 시작 위치를 컨트롤
      for i in range(N - M + 1):
          cnt = 0
          for j in range(M):
              if t[i + j] == p[j]:
                  cnt += 1
              else:
                  break
  
          if cnt == M:
              return i
  
      return -1
  ```

- 

#### 2. KMP 알고리즘

- 불일치가 발생한 텍스트 문자열의 앞 부분에 어떤 문자가 있는지를 미리 알고 있으므로, 불일치가 발생한 앞 부분에 대하여 다시 비교하지 않고 매칭을 수행
- 패턴을 전처리하여 배열 next[M]을 구해서 잘못된 시작을 최소화함
- O(M+N), 최선의 경우 : O(N)

#### 3. 보이어 - 무어 알고리즘

- 오른쪽에서 왼쪽으로 비교
- 대부분의 소프트웨어에서 채택하고 있는 알고리즘
- 패턴의 오른쪽 끝에 있는 문자가 불일치하고 이 문자가 패턴 내에 존재하지 않는 경우, 이동 거리는 패턴의 길이만큼 된다.
- 문자열에 사용되는 문자셋이 클수록 좋음
- 입력에 따라 다르지만 일반적으로 O(N)보다는 덜 든다. 하지만 최악의 경우에는 O(MN)

<br>

### 참고

#### 1. 문자열 암호화

- 시져 암호화
- 단일 치환 암호화 : 복호화를 하기 위해서는 모든 키의 조합이 필요(26!)
- 비트열의 암호화(exclusiveOR) : 암호화 키와 해독 키가 같음

#### 2. 문자열 압축

- Run - lenght  encoding algorithm
  - ABBBBBA → A1B5A1
- 허프만 코딩 알고르즘
  - 많이 사용된다.

<br>

``02.18``

:heavy_check_mark: 시간

> - 어떠한 값이 있는지 없는지 확인할 때에는 list보다 set, dict을 사용하는 것이 빠르다.

<br>

:memo: bit 연산

> - 실행 속도가 빠르다.
>
> - 메모리를 적게 사용한다.
>
>   ```python
>   mid = (s + e) // 2
>   mid = (s + e) >> 1  # 이렇게 사용하는 것이 속도가 빠름
>   
>   # 집합을 표현하는데 많이 사용(16진수)
>   U = 'ABCDEFGH'
>   A = 0x31  # 0011 0001 (A, E, F)
>   B = 0xd2  # 1101 0010 (B, E, G, H)
>   ```

<br>

:heavy_check_mark: 음수 계산

> - print(-5 // 2) : -3 (내림)
> - print(int(-5 //2 )) : -2  → 이렇게 사용 (0.5를 버림), 다른 언어들의 동작방식과 같음

<br>

``02.19``

:heavy_check_mark: 문자열 리스트 입력 후 세로로 읽기

> - 만약에 len(i) = 5, len(4)이면 조건을 넣어서 없는 인덱스 부분을 무시하고 진행한다.
> - try / except를 사용하여 pass 하는 것도 방법!



🐣정리해야 할 것!

- 문자열 입력 시 차이 (input / input.split)
  - abcde 
  - a b c d e
- 입력 시 list(map), map 사용시 int, input.split / input.split => Test
- 위에 결과들에서 for _ in range(N)을 썼을 때도 확인!
- 알고리즘 for문과 while 둘 다 구현 가능하게!
- N - M + 1 index를 사용하는 경우
- for문 사용시 어디서부터 씌우고 index는 어떻게 할지!

<br>

:heavy_check_mark: 시간 초과 문제

> - input() 보다는 sys.readline() 사용
> - 빈 리스트에 append()로 추가하는 것보단 입력 받을 개수만큼 초기화된 리스트에 인덱스를 이용해서 접근하고 그 위치에 직접 입력을 받음
> - 줄을 바꿔가면서 출력할 때, '\n'을 사용
> - for문마다 출력하지 말고 문자열 변수에 저장해놓고 한번에 출력!

<br>

``02.22``

### Stack

```python
# Stack
# 메모리 미리 생성
stack_size = 3
stack = [0] * stack_size  # 저장소, python에서는 이렇게 잘 안씀
top = -1  # 초기값을 -1로

# 2가지 대표적인 연산(관례적으로 쓰는 함수명 push, pop)
def push(item):
    # 아직 '데이터가 들어와있지 않다'를 표현하기 위해 top 이용(-1 : 없는 것을 가르킴, python 제외)
    # top은 항상 마지막에 삽입된 자료를 가르킨다.
    global top  # 여기서 top 값을 확인해봐야함
    if top == stack_size -1:
        return  # 일반적으로 return보다는 try / except를 통해서 알려줌
                 # 정상적인 실행상황이 아님
                 # 알고리즘 문제를 풀때는 이런 상황이 나오면 안됨, 항상 집어넣을 수 있어야함
                 # 충분히 담을 수 있는 공간을 확보 후 진행(stact이 다 차는 상황이 발생하면 안됨!!)
    top += 1
    stack[top] = item

def pop():
    global top
    # pop에서는 빈 stack인 상황이 나올 수 있음
    # 빈 공간일때는 항상 주의!!
    # 여기서 만들지 않고 따로 만들어줌!! (실제 값과 섞일 수가 있어서)
    ret = stack[top]  # 반환
    top -= 1
    return ret  # 값이 남아있긴하지만 덮어씌워지기 때문에 상관없음(굳이 지울 필요가 없음)

def isEmpty():
    return top == -1

push(1); push(2); push(3)
print(stack)
## [1, 2, 3]
print(pop()); print(pop()); print(pop());
## 3 2 1
print(stack, top)  # 값이 남아있긴하지만 덮어씌워지기 때문에 상관없음
## [1, 2, 3] -1
push(10)
print(stack, top)
[10, 2, 3] 0

push(1); push(2); push(3)
while not isEmpty():
    print(pop())
# 2 1 10

# stack은 역순으로 나와야하는 경우에 사용

# 괄호검사 : 여는 괄호를 기록 -> 닫는 괄호는 역순으로 나와야함
# 여는 괄호는 집어넣고 뺄때는 뺼 것이 있는지 확인하고 뺌
# 다 확인 후 남아있는지 체크
```

<br>

``02.23``

### 그래프

- 그래프는 아이템(사물 또는 추상적 개념)들과 이들 사이의 연결관계를 표현
- 그래프는 정점(Vertex)들의 집합과 이들을 연결하는 간선(Edge)들의 집합으로 구성된 자료 구조
- 연결 방법
  - 연속적 : 배열
  - 비연속적 : 연결 리스트
- 두 정점 사이에 간선이 있으면 인접해있다고 한다.

<br>

### 변수

- 지역변수와 매개변수는 함수의 실행이 끝나면 메모리에서 날아감(pop)

- ```python
  # 재귀의 Depth(DFS 사용시에 고려)
  import sys
  print(sys.getrecrusionlimit())  ## 1000
  sys.setrecrusionlimit(10000)
  print(sys.getrecrusionlimit)  ## 10000
  ```

- 변수는 생명주기(생성, 소멸)과 스코프(범위)가 있다.

<br>

``02.24``

### 중위표기법(infix notation)

- 연산자를 피연산자의 가운데 표기하는 방법

- ex) A + B

### 후위표기법(postfix notation)

- 연산자를 피연산자 뒤에 표기하는 방법

- AB +

<br>

#### 중위표기법의 후위표기법 변환 방법

- ```python
  A*B-C/D
  1단계 : ((A*B)-(C/D))
  2단계 : ((A B)*(C D)/)-
  3단계 : AB*CD/-
  ```

- ```python
  # 스택 이용
  1. 입력 받은 중위 표기식에서 토큰을 읽는다
  *토큰 : A, B, C, D, +, * ...
      
  2. 토큰이 피연산자이면 토큰을 출력
  
  3. 토큰이 연산자일때, 이 토큰이 스택의 top에 저장되어 있는 연산자보다 우선순위가 높으면 스택에 push하고, 그렇지 않다면 스택 top의 연산자의 우선순위가 토큰의 우선순위보다 작을 때까지 스택에서 pop한 후 토큰의 연산자를 push한다. 만약 top에 연산자가 없으면 push한다.
  
  4. 토큰이 오른쪽 괄호')'이면 스택 top에 왼쪽 괄호 '('가 나올 때까지 스택에 pop연산을 수행하고 pop한 연산자를 출력한다. 왼쪽 괄호를 만나면 pop만 하고 출력하지 않는다.
  
  5. 중위 표기식에 더 읽을 것이 없다면 중지하고, 더 읽을 것이 있다면 1부터 다시 반복한다.
  
  6. 스텍에 남아 있는 연산자를 모두 pop하여 출력한다.
  
  ## 스택 밖의 왼쪽 괄호는 우선 순위가 가장 높으며, 스택 안의 왼쪽 괄호는 우선 순위가 가장 낮다.
  ```

<br>

### 백트래킹(Backtrackig)

- 해를 찾는 도중에 막히면(즉, 해가 아니면) 되돌아가서 다시 해를 찾아가는 기법
- 최적화(Optimization) 문제와 결정(decision) 문제를 해결할 수 있다.
- 결정 문제 : 문제의 조건을 만족하는 해가 존재하는지의 여부를 yes or no로 답하는 문제
  - ex) 미로 찾기, n-Queen 문제, Map coloring, 부분 집합의 합(Subset Sum) 문제 등

<br>

#### 백트래킹과 깊이우선탐색과의 차이

- 어떤 노드에서 출발하는 경로가 해결책으로 이어질 것 같지 않으면 더 이상 그 경로를 따라가지 않음으로써 시도의 횟수를 줄임(Prunning 가지치기)
- 백트래킹은 불필요한 경로를 조기에 차단

<br>

### 부분집합 구하기

- 어떤 집합의 공집합과 자기자신을 포함한 모든 부분집합을 powerset이라고 하며 구하고자 하는 어떤 집합의 원소 개수가 n일 경우 부분집합의 개수는 2^n이 나온다.

<br>

:heavy_check_mark: 백트래킹을 이용하여 부분집합을 구하는 방법과 순열을 구하는 방법 추가 필요!!

