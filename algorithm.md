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