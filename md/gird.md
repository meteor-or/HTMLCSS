# grid

## display:gird

- 2차원(행row과 열column)의 레이아웃 시스템으로 부모 요소(grid container)와 자식 요소(grid item)으로 구성되어 있다.

## 1 grid-template

### 1.1. grid-template-rows

```
  grid-template-rows:200px 100px 50px 150px;/* 1행 2행 3행 4행 */
  grid-template-rows:200px 100px;/* 1행 2행 */
  grid-template-rows:20% 20% 25% 35%;/* 높이값이 지정되지 않으면 비율에 맞춰 조정 */
  grid-template-rows:10vw 10vw 15vw 25vw;
  grid-template-rows:10vh 6rem;
  grid-template-rows:1fr 2fr 3fr 1fr;/* fr:공간 비율, 분수 fraction, 1/7 2/7 3/7 1/7
```

### 1.2. grid-template-columns

```
grid-template-columns:200px 100px 80px 140px;
grid-template-columns:200px 100px;/* 1열:200px 2열:100px, 아이템의 수와 상관없이 최종 2열을 유지 */
grid-template-columns:10vh 16rem 40%;/* 최종 3열을 유지 */
grid-template-columns: 50%;/* 1열 */
grid-template-columns: 1fr;/* 1열 */
grid-template-columns: 1fr 1fr;/* 2열 */
grid-template-columns: 1fr 1fr 1fr;/* 3열 */
grid-template-columns: 1fr 1fr 2fr 1fr;/* 4열, 1/5 1/5 2/5 1/5 */
```

## 2 최소값Min최대값Max

```
grid-template-rows:minmax(80px, auto) minmax(auto,200px);/* height */
grid-template-columns: minmax(100px, auto) minmax(auto,200px) minmax(50px, 300px);/* width */
grid-template-columns: minmax(auto, 200px) 1fr 9rem;
```

## 3 gap

- 열과 행의 간격(grid gutter)

```
row-gap:30px;/* 행과 행사의 간격 */
column-gap:3vw;/* 열과 열사이의 간격 */
```

## 4 repeat

- repeat(반복횟수,크기); 행과 열의 값 반복

```
grid-template:100px 100px / 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
grid-template:100px 100px / repeat(7, 1fr);/* repeat(열, 크기) */
grid-template:repeat(3,100px) / 100px repeat(6, 1fr);/* 1열:100px 2~7열:1fr */
grid-template:repeat(3,100px) / 100px repeat(5, 1fr) minmax(auto,300px);/* 1열:100px 2~6열:1fr 7열:minmax */
```

## 5 grid-column, grid-row

- 그리드 라인에 따른 위치 선정. 좌표 값

### 5.1. grid-row-start, end

```
grid-row-start: 1;
grid-row-end: 4;
```

### 5.2. 축약형

```
/* grid-row-start:2 ;
grid-row-end: 5;
grid-column-start:2 ;
grid-column-end: 4; */

grid-row: 2 / 5;/* start / end*/
grid-column: 2/4;
```

### 5.3. span

```
grid-row: 2 / span 3; /* 그리드라인 2번부터 3개의 영역을 합침 */
grid-column: 1 / span 2; /* */
```

## 6 gird line naming

```
/* [사용자지정라인이름] 아이템 크기 [사용자지정라인이름] */
grid-template-rows:[row1] 100px [row2] 100px [row3];
grid-template-columns:[col1] 1fr [col2] 1fr [col3] 1fr [col4];
```

## 7 gird-template-area

- 이름으로 영역 지정
- "인용부호 안의 값은 하나의 행 안의 하나의 셀" 1번째 행
- "txt txt" 2번째 행. 텍스트 다음 띄어쓰기를 통해 셀 표시
- ". none" 3번째 행. 비움

````
grid-template-areas:
  "header header"
  "contents aside"
  ". ."
  "footer footer";```
````

## 8 justify-content

- 그리드 영역 지정

## 9 item 정렬

### align-items

- 그리드 아이템 안에서의 열 정렬

```
  align-items: start;
  align-items: end;
  align-items: center;
  align-items: stretch
```

### justify-items

- 그리드 컨테이너 안의 행row 정렬. 하나일 때

```
  justify-items: stretch;
  justify-items: start;
  justify-items: center;
  justify-items: end;
```

### place-item

`place-items:start center;/* align-items justify-items`

### justify-self

### align-self

### place-self

## 10 auto-fit, auto-fill

- minmax()함수없이 auto, 1fr 단독 사용시 적용되지 않음

### 10.1. auto-fit

- 여백이 남지 않게 아이템의 크기를 늘려 컨테이너의 영역을 채움

### 10.2. auto-fill

- 여백이 남음. 컨테이너 영역을 가능한 많은 아이템으로 채움

```
  주로 minmax()함수와 함께 '최소,최대' 값 사용
  repeat(auto-fill, 100px);
  repeat(auto-fit, 20%);
  repeat(auto-fill, minmax(auto, 100px));
  repeat(auto-fit, minmax(100px, auto));
  repeat(auto-fit, minmax(100px, 1fr));
```
