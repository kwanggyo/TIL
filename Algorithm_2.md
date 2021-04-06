# Algorithm_2

# `04.05`

## 트리

- 비선형 구조
- 원소들 간에 1:n 관계를 가지는 자료구조
- 원소들 간에 계층관계를 가지는 계층형 자료구조
- 상위 원소에서 하위 원소로 내려가면서 확장되는 트리모양의 구조

### 정의

> - 한 개 이상의 노드로 이루어진 유한 집합이며 다음 조건을 만족한다.
>   - 노드 중 최상위 노드를 루트(root)라 한다.
>   - 나머지 노드들은 n(>=0)개의 분리 집합 T1, ..., TN으로 분리될 수 있다.
> - 이들 T1, ..., TN은 각각 하나의 트리가 되며(재귀적 정의) 루트의 부 트리(subtree)라 한다.
> - 단말노드(리프노드(leaf node)) : 마지막에 있는 노드(자식이 없는 노드)

### 용어

> - 노드(node) - 트리의 원소
> - 간선(edge) - 노드를 연결하는 선, 부모 노드와 자식 노드를 연결
> - 루트 노드(root node) - 트리의 시작 노드(부모가 없는 노드)
>
> - 형제 노드(sibling node) - 같은 부모 노드의 자식 노드들
> - 조상 노드 - 간선을 따라 루트 노드까지 이르는 경로에 있는 모든 노드들
> - 서브 트리(subtree) - 부모 노드와 연결된 간선을 끊었을 때 생성되는 트리
> - 자손 노드 - 서브 트리에 있는 하위 레벨의 노드들
> - 차수(degree)
>   - 노드의 차수 : 노드에 연결된 자식 노드의 수
>   - 트리의 차수 : 트리에 있는 노드의 차수 중에서  가장 큰 값(연결된 노드의 수 중 가장 큰 값)
>   - 단말 노드(리프 노드) : 차수가 0인 노드, 자식 노드가 없는 노드
> - 높이(Level)
>   - 노드의 높이 : 루트에서 노드에 이르는 간선의 수, 노드의 레벨
>     - 책마다 시작값(0, 1)이 다름, 일반적으로 0
>   - 트리의 높이 : 트리에 있는 노드의 높이 중에서 가장 큰 값, 최대 레벨

<br>

## 이진 트리

- 모든 노드들이 2개의 서브 트리를 갖는 특별한 형태의 트리

- 각 노드가 자식 노드를 최대한 2개 까지만 가질 수 있는 트리

  - 왼쪽 자식 노드(left child node)
  - 오른쪽 자식 노드(right child node)

- **자식노드의 수가 무조건 2개가 아니라 없거나 1개일 수도 있다!**

- 모양만 보고 이진트리인지 알 수는 없다. 1:N 관계로 들어왔을 수도 있기 때문에, 이진트리 조건에 만족한다 정도(자식이 2개 이하)

- 레벨 i에서의 노드의 최대 개수는 2^i개

- 높이가 h인 이진 트리가 가질 수 있는 노드의 최소 개수는 (h+1)개가 되며, 최대 개수는 (2^(h+1) -1)개가 된다.

  - ex) h=3 이면 최대개수 = 2^3 + 2^2 + 2^1 + 2^0

  - 등비수열이나 이진수로 구할 수 있다!

### 포화 이진 트리(Full Binary Tree)

> - 모든 레벨에 노드가 포화 상태로 차 있는 이진 트리(전부다 2개씩)
> - 높이가 h일 때, 최대의 노드 개수가 (2^(h+1) -1)의 노드를 가진 이진 트리
> - 루트를 1번으로 하여 2^(h+1) -1까지 정해진 위치에 대한 노드 번호를 가짐
> - 따로 취급하기 위해서 이름을 붙인 것!

### 완전 이진 트리(Complete Binary Tree)

> - 높이가 h이고 노드 수가 n개일 때 (단, h+1 <= n <= 2^(h+1) -1), 포화 이진 트리의 노드 번호 1번부터 n번까지 빈 자리가 없는 이진 트리
> - 마지막 레벨 까지 꽉 차있을 수 도 있고 아닐 수도 있음, 대신 중간에 비어있으면 안됨

### 편향 이진 트리(Skewed Binary Tree)

> - 높이 h에 대한 최소 개수의 노드를 가지면서 한쪽 방향의 자식 노드만을 가진 이진 트리
>   - 왼쪽 편향 이진 트리
>   - 오른쪽 편향 이진 트리
> - 비선형 자료의 장점이 없어진 모양 --> 선형 모양
>   - 리스트를 앞에서부터 찾는 것과 같음

### 순회(traversal)

> - 트리의 각 노드를 중복되지 않게 전부 방문(visit) 하는 것을 말하는데 트리는 비 선형 구조이기 때문에 선형구조에서와 같이 선후 연결 관계를 알 수 없다. 따라서 특별한 방법이 필요!
> - 순회 : 트리의 노드들을 체계적으로 방문하는 것
> - 3가지의 기본적인 순회방법
>   - 전위순회(preorder traversal) : VLR
>     - 부모 노드 방문 후, 자식 노드를 좌, 우 순서로 방문
>   - 중위순회(inorder traversal) : LVR
>     - 왼쪽 자식노드, 부모노드, 오른쪽 자식노드 순으로 방문
>     - 부모노드부터 방문하지만 처리하지는 않고 왼쪽 자식노드로 가서 먼저 처리
>   - 후위순회(postorder traversal) : LRV
>     - 자식노드를 좌우 순서로 방문한 후, 부모노드로 방문
> - 전위와 후위를 같이 사용도 가능!
> - 순회하면서 꺼내는 것만이 아니라 집어넣을 수도 있음
> - 손으로 따라갈 수 있어야함!
> - DFS로 할 수 있지만 재귀로 구현함(구분하는 목적이 있기 때문에)
>
> #### 1. 전위 순회(preorder traversal)
>
> > - 수행 방법
> >   1. 현재 노드 n을 방문하여 처리 - V
> >   2. 현재 노드 n의 왼쪽 서브트리로 이동 - L
> >   3. 현재 노드의 n의 오른쪽 서브트리로 이동 - R
>
> #### 2. 중위 순회(inorder traversal)
>
> > - 수행 방법
> >   1. 현재 노드 n의 왼쪽 서브트리로 이동 - L
> >   2. 현재 노드 n을 방문하여 처리 - V
> >   3. 현재 노드의 n의 오른쪽 서브트리로 이동 - R
>
> #### 3. 후위 순회(postorder traversal)
>
> > - 수행 방법
> >   1. 현재 노드 n의 왼쪽 서브트리로 이동 - L
> >   2. 현재 노드의 n의 오른쪽 서브트리로 이동 - R
> >   3. 현재 노드 n을 방문하여 처리 - V

### 표현(어떤 이진 트리냐에 따라 다름)

> - 배열을 이용한 이진 트리의 표현
>   - 이진 트리에 각 노드 번호를 부여
>   - 루트의 번호를 1로 함
>   - 레벨 n에 있는 노드에 대하여 왼쪽부터 오른쪽으로 2^n 부터 2^(n+1) -1 까지 번호를 차례로 부여
> - 노드의 성질(포화 이진 트리)
>   - 노드 번호가 i인 노드의 부모 노드 번호 : l_i/2_l (floor 연산 i/2를 넘지 않는 가장 큰 값)
>     - int(-3/2) = -1, -3//2 = -2(floor연산)
>   - 노드 번호가 i인 노드의 왼쪽 자식 노드 번호 : 2*i
>   - 노드 번호가 i인 노드의 오른쪽 자식 노드 번호 : 2*i + 1
>   - 레벨 n의 노드 번호 시작 번호 : 2^n
> - 노드 번호를 배열의 인덱스로 사용
> - 배열을 이용한 이진 트리 표현의 단점
>   - 편향 이진 트리의 경우에 사용하지 않는 배열 원소에 대한 메모리 공간 낭비가 발생
>   - 트리의 중간에 새로운 노드를 삽입하거나 기존의 노드를 삭제할 경우 배열의 크기 변경이 어려워 비효율적
> - 단점을 보완하기 위해 연결리스트를 이용할 수 있다.
> - 주의!!(명시 되어있는지 확인!!)
>   - 포화 이진 트리인지 여부
>   - 루트가 1번이다 X
>   - 부모번호가 더 작은 경우가 많지만 무조건은 아님, 더 클 수가 있음

<br>

## 수식 트리

- 수식을 표현하는 이진 트리
- 수식 이진 트리(Expression Binary Tree)라고 부르기도 함
- 연산자는 루트 노드이거나 가지 노드
- 피연산자는 모두 잎 노드

> - 중위 순회 : A / B * C * D + E
> - 후위 순회 : A B / C * D * E +
> - 전위 순회 : + * * / A B C D E

<br>

## 이진 탐색 트리

- 탐색 작업을 효율적으로 하기 위한 자료 구조
- 모든 원소는 서로 다른 유일한 키를 갖는다.
- key(왼쪽 서브트리) < key(루트 노드) < key(오른쪽 서브트리)
- 왼쪽 서브트리와 오른쪽 서브트리도 이진 탐색 트리다.
- 중위 순회하면 오름차순으로 정렬된 값을 얻을 수 있다.

### 탐색 연산

> - 루트에서 시작한다.
> - 탐색할 키 값x를 루트 노드의 키 값과 비교한다.
>   - (키 값 x = 루트노드의 키 값)인 경우 : 원하는 원소를 찾았으므로 탐색연산 성공
>   - (키 값 x < 루트노드의 키 값)인 경우 : 루트노드의 왼쪽 서브트리에 대해서 탐색연산
>   - (키 값 x > 루트노드의 키 값)인 경우 : 루트노드의 오른쪽쪽 서브트리에 대해서 탐색연산
> - 순환하면서 탐색 연산
> - 이진 탐색 트리(좌우가 잘 맞춰진) 장점 : 선형으로 탐색하는 것보다 빠름, 탐색 깊이를 주일 수 있음 → 탐색 시간을 줄임

### 삽입 연산

> - 먼저 탐색 연산을 수행
>   - 삽입할 원소와 같은 원소가 트리에 있으면 삽입할 수 없으므로, 같은 원소가 트리에 있는지 탐색하여 확인
>   - 탐색에서 탐색 실패가 결정되는 위치가 삽입 위치
> - 탐색 실패한 위치에 원소를 삽입

### 성능

> - 탐색(searching), 삽입(insertion), 삭제(deletion) 시간은 트리의 높이 만큼 시간이 걸림
>   - O(h), h: BST의 깊이(height)
> - 평균의 경우
>   - 이진 트리가 균형적으로 생성되어 있는 경우
>   - O(log n)
> - 최악의 경우
>   - 한쪽으로 치우친 경사 이진트리의 경우
>   - O(n)
>   - 순차탐색과 시간복잡도가 같음
> - 얼마나 좌우균형이 맞춰서 삽입이 이루어지느냐에 따라 성능이 달라짐
> - 검색 알고리즘의 비교
>   - 배열에서의 순차 검색 : O(N)
>   - 정렬된 배열에서의 순차 검색 : O(N)
>   - 정렬된 배열에서의 이진 탐색 : O(logN)
>     - 고정 배열 크기와 삽입, 삭제 시 추가 연산 필요
>   - 이진 탐색트리에서의 평균 : O(logN)
>     - 최악의 경우 : O(N)
>     - 완전 이진 트리 또는 균형트리로 바꿀 수 있다면 최악의 경우를 없앨 수 있음
>       - 새로운 원소를 삽입할 때 삽입 시간을 줄인다.
>       - 평균과 최악의 시간이 같다. O(logN) → 레드블랙트리
> - 해쉬 검색 : O(1)
>   - 추가 저장 공간이 필요

<br>

## 힙(heap)

- 완전 이진 트리에 있는 노드 중에서 키값이 가장 큰 노드나 키값이 가장 작은 노드를 찾기 위해서 만든 자료구조
- 왼쪽과 오른쪽 자식의 대소 관계는 중요하지 않고 부모 자식 간의 대소 관계를 따진다.
- 최대 힙(max heap)
  - 키값이 가장 큰 노드를 찾기 위한 **완전 이진 트리**
  - 부모노드의 키값 > 자식노드의 키값
  - 루트 노드 : 키값이 가장 큰 노드
- 최소 힙(min heap)
  - 킥값이 가장 작은 노드를 찾기 위한 **완전 이진 트리**
  - 부모노드의 키값 < 자식노드의 키값
  - 루트 노드 : 키값이 가장 작은 노드
- 힙의 키를 우선순위로 활용하여 우선순위 큐를 구현할 수 있다.

### 삽입

> - 마지막 노드 + 1에 삽입
> - 삽입 후 부모와 비교하여 이동(p = c // 2)

### 삭제

> - 루트 노드의 원소만을 삭제할 수 있다.
> - 루트 노드의 원소를 삭제하여 반환한다.
> - 힙의 종류에 따라 최대값 또는 최솟값을 구할 수 있다.
> - 마지막 노드를 삭제해야함(last를 감소)
> - 순서
>   - 루트 노드의 원소 삭제 - 마지막 노드 삭제 - 삽입노드 < 자식노드이면 자리 바꾸기 - 자리 확정

<br>

## :memo: 

>### 트리
>
>- 루트로부터 그래프를 탐색하는 것
>- 데이터를 의미 있는 구조로 저장할 때 트리를 자주 사용함(폴더 구조)
>- 자연스럽게 그룹으로 나누어짐
>- 이진 트리는 나중에 이진 탐색에 활용함
>- 1차 배열 2개를 쓰는 방법 / 2차 배열  한 개를 쓰는 방법이 있음 → 2개만 있기 때문에
>- 이진 트리를 저장할 때
>  - 각 노드에 대해서 왼쪽 자식이 있는지 없는지, 왼쪽 자식이 누구인지, 부모가 누구인지
>  - → 자식 정보와 부모 정보를 저장
>- 트리를 순회할 때는 방문 표시를 안해도 된다!
>  - 한 방향으로만 순회하기 때문에(부모 → 자식)
>  - 되돌아가지 않아도 된다. + 사이클이 없음
>  - 대신 마지막에 왔는지 안왔는지를 판단해야함(더이상 갈 곳이 있는지)
>    1. 지금 보고있는 노드가 단말노드인지 판단
>    2. 특별한 노드를 하나씩 달아놓아서 판단(공백 노드(NULL node))
>       - 왼쪽과 오른쪽 자식이 없다면 없다라는 표시
>- 위치를 정해두고 없으면 비워두는 형식으로 저장한다.
>- Heap : 완전이진트리 형태의 구조를 저장함 - 스택과 비슷한 개념으로 FILO, 1차 배열 형태로 저장 → 정확하지 않음
>- 노드 수가 V 라면 간선 수는 V-1 → 이렇게 해야 사이클이 없음
>
>### 이진 트리
>
>- 이진트리 순회 : 모든 노드를 3번 거쳐간다.
>  - 처음 노드에 진입할 때
>  - 왼쪽 자식에서 돌아올 때
>  - 오른쪽 자식에서 돌아올 때
>- DFS 방식 - 왼쪽 자식 먼저 가본다.
>
>### 참고
>
>- C나 java에서는 입력이 각 줄마다 몇개씩 들어오는지 알려줘야한다!
>- 완전이진트리와 같은 문제는 노드의 개수로 입력의 개수로 알 수 있다.

<br>

# `04.06`

## 최소공통조상(LCA)

- 트리에서 기본적으로 풀어야하는 유명한 문제!
- 트리 : 문자열 처리에서 많이 활용됨
  - 패턴 매칭, 압축

<br>

## 이진탐색트리

- 왜 사용하는가? 배열에 저장에서 쓰거나, 이진트리를 쓰면 되지 않나?

  - 배열에서 정렬을 하고 찾을 때 O(logN)
  - 이진탐색트리에서 찾을 때 O(logN)

  → `계속 정렬된 상태를 유지하기 위해서 사용`

  - 찾을 때는 O(logN)으로 같지만 삽입하고 삭제할 때 다름
  - 배열에 삽입 삭제할 경우는 한칸씩 앞으로 밀거나 뒤로 미는 작업을 추가적으로 해야 함, 최악의 경우에는 O(N)이 걸림
  - `이진탐색트리는 삽입하거나 삭제할 때 O(logN)이 걸림`
  - 일반 상황에서 자료의 배치는 빈번하게 변하는데 그 와중에 탐색을 할 때 용이

- 어떤 노드를 루트로 사용하더라도 높이 차이가 1이내로 들어오도록 해야 함

- 단말노드까지 가도 못찾는 경우 : 탐색 실패(최악의 경우 트리의 높이 만큼의 경우의 수가 필요함) → 높이를 logN으로 만듦

<br>

## 해쉬 검색

- O(1) : 상수 시간 → 자료가 많던 적던 찾는 시간이 일정, 저장 공간이 필요(메모리)
- 메모리 사용량을 늘리고 시간을 줄인다.
- 배열에서 index를 알고 바로 찾아가는 경우 O(1)
- python의 Dictionary가 해싱으로 구성되어 있다.
- 추가적인 단점
  - 저장된 순서를 알 수 없음
  - 자료가 있는지 없는지 탐색은 빠르지만 읽어오는 순서는 알 수 없음

### 직접 번지 테이블 방식

> - ex) 회사의 사번(unique key value)을 통해서 값을 찾음, 사번에 해당하는 메모리 공간 확보 필요
> - 키 값을 배열의 index로 하여 원하는 값을 바로 찾음(해싱)
> - 직접 매핑은 메모리를 너무 많이 사용(ex. naver의 회원가입 때 정보를 저장할 메모리 - 너무 큼)
> - Key값에 해당하는 값을 mapping시켜줌 : 해시함수가 매핑시켜주는 역할을 한다!

### 간접 번지 테이블 방식

> - 해시함수를 통해 변환시켜서 찾아가는 것
> - 계산에 의해서 바꿔서 나오는데 우연히 그 값이 같게 나와서 충돌이 일어날 수 있다. 그에 따른 해결방법이 있다.
>   - 해결 방법은 나중에 배우는 걸로..