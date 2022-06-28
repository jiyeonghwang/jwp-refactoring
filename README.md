# 키친포스

## 요구 사항

### 메뉴 그룹
메뉴 그룹 이릅으로 구성
#### 메뉴 그룹 기능
- 메뉴 그룹 등록
- 메뉴 그룹 전체 조회

### 메뉴
- 메뉴 이름, 가격, 메뉴 그룹, 상품 리스트로 구성
#### 메뉴 기능
- 메뉴 등록
  - 가격이 `0` 보다 작은 경우 등록 불가
  - 메뉴 그룹이 등록되지 않은 경우 등록 불가
  - 메뉴 가격이 상품 리스트의 총 가격보다 큰 경우에만 등록 가능
- 메뉴 전체 조회

### 주문
- 주문 테이블, 주문 상태, 주문 시간, 주문 항목 리스트로 구성
#### 주문 기능
- 주문 등록
  - 주문 항목 리스트가 없는 경우 등록 불가
  - 테이블이 미등록인 경우 등록 불가
  - 빈 테이블인 경우 등록 불가
- 주문 전체 조회
- 주문 상태 변경
  - `조리`, `식사` 상태로 변경 가능

### 상품
- 상품 이름, 가격으로 구성
#### 상품 기능
- 상품 등록
  - 가격이 `0` 이하인 경우 등록 불가
- 상품 전체 조회

### 단체 지정
- 생성 날짜, 주문 테이블 리스트로 구성
#### 단체 지정 기능
- 단체 지정 등록
  - 주문 테이블 리스트가 `2` 보다 작은 경우 등록 불가
- 단체 지정 해제
  - 주문 테이블 중 `조리`, `식사` 상태인 경우 해제 불가

### 주문 테이블
- 단체 지정 아이디, 방문한 손님 수로 구성
#### 주문 테이블 기능
- 주문 테이블 등록
  - 처음 등록 시 단체 지정 아이디는 `NULL`로 등록
- 주문 테이블 전체 조회
- 주문 테이블 빈 테이블로 상태 변경
  - 단체 지정 아이디가 있는 경우 변경 불가능
  - `조리`, `식사` 상태인 경우 변경 불가능
- 방문한 손님 수 변경
  - `0` 명보다 작은 경우 변경 불가능
  - 미등록된 주문 테이블인 경우 변경 불가능 

## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
