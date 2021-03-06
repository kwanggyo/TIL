# MEMO

### 입력

- 문자열로 입력을 받을 때

  ```python
  order = input().split()
  # 입력 : push 1
  print(order)
  ## ['push', '1']
  # 리스트 형태로 출력이 됨
  ```

- 입력의 단위는 행 단위로 끊어진다!!

  ```python
  while True:
      N = input()
      if N == '.':
          break
  # 입력이 몇 줄인지 안알려주었을 때, 
  # . 이 나올때 종료하라는 조건(종료조건 예시)을 알려준다.
  ```

- 빈 행렬을 만들 때, 개수가 1씩 늘어나는 삼각형처럼 하려면

  ```python
  arr = [[1] * i for i in range(1, N + 1)]
  ```

  