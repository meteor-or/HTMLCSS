# Flex

## 1. 개념

- 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때 사용.
  상속되지 않음
- 부모 박스(flex container)와 자식 박스(flex item)로 구성
- flex-container: flex-direction, flex-wrap, justify-content, align-item...
  flex-item: flex. flex-grow, flex-shrink, flex-basis, order...

## 2. flex-direction:

바로 밑에 있는 item을 제어한다.

1. `flex-direction:row`  
   기본값. 플렉스 아이템 왼쪽에서 오른쪽으로 배치. 주축(main axis)은 가로 교차축(cross axis)은 세로
1. `flex-direction:row-reverse`  
   역방향 가로로 배치. 주축은 가로 교차축은 세로
1. `flex-direction:column`
1. `flex-direction:column-reverse`

## 3. align-items:

1. `align-items:flex-start;`  
    교차축 기준.
   (flex-direction을 기준으로 주축이 정해진다. 주축의 반대 방향이 교차축)  
    시작점에서 끝나는 점으로 정렬
2. `align-items:flex-end`  
   교차축 기준으로 플렉스 아이템과 여백 정렬
3. `align-items:stretch;`  
   기본값. 높이값이 지정되지 않은 경우 플렉스 아이템 확장 정렬
4. `align-items:baseline;`  
   플렉스 아이템 시작점에서 배치되는 글자의 베이스라인에 맞춤
5. `align-items:center;`  
   교차축 기준 중앙 정렬, 자주 사용함

   세로 중앙 정렬이 쉬워짐

## 4. align-content;

1. `align-content:stretc;h` (기본값)  
   높이값이 지정되지 않은 경우 확장 정렬

2. `align-content:flex-start;`  
   교차축 기준 시작점에서 정렬
3. `align-content:flex-end;`  
   교차축 기준 끝나는 점에서 정렬

## 5. flex-grow

- 증가비율(flex-grow) 감소비율(flex-shrink) 기본비율 (flex-basis)
- 플렉스 아이템에 적용.
- 아이템의 증가, 감소, 기본 비율을 설정하는 단축 속성

### 5.1. flex-grow: 0;

숫자가 클수록 더 큰 영역을 가짐. 가변값이 아니거나 0인 경우 적용되지 않음. 0,1

### 5.2. flex-shrink: 1;

숫자가 클수록 더 큰 영역이 감소. 가변갑이 아니거나 0인 경우 적용되지 않음.

### 5.3.flex-basis:auto; 기본 너비 값 설정.

auto인 경우 width, height등의 속성으로 너비 설정 가능하나 단위값이 주어진 경우 설정할 수 없음.

## 6. flex-wrap

1. `flex-wrap:nowrap;`  
   기본값. 플렉스 아이템 한 줄 배치
2. `flex-wrap:wrap; `  
   줄바꿈. 여러 줄 배치
3. `flex-wrap: wrap-reverse;`  
   역방향으로 줄바꿈

## 7. flex-flow

1. `flex-wrap:nowrap;` (기본값)
2. `flex-flow:row nowrap;`
3. `flex-flow:column;`
4. `flex-flow:row-reverse wrap;`
