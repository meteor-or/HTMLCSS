# FlexibleBox
## 개념
* 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때 사용.
상속되지 않음
* 부모 박스(flex container)와 자식 박스(flex item)로 구성
* flex-container: flex-direction, flex-wrap, justify-content, align-item...
flex-item: flex. flex-grow, flex-shrink, flex-basis, order...

## align-items;
1. flex-start  
	교차축 기준. 시작점에서 끝나는 점으로 정렬
2. flex-end  
	교차축 기준으로 플렉스 아이템과 여백 정렬
3. stretch  
	기본값. 높이값이 지정되지 않은 경우 플렉스 아이템 확장 정렬
4. baseline  
	플렉스 아이템 시작점에서 배치되는 글자의 베이스라인에 맞춤
5. center  
	교차축 기준 중앙 정렬, 자주 사용함
	
	세로 중앙 정렬이 쉬워짐

## align-content;
1. stretch (기본값)  
높이값이 지정되지 않은 경우 확장 정렬 

2. flex-start  
	교차축 기준 시작점에서 정렬
3. flex-end  
	교차축 기준 끝나는 점에서 정렬

## flex-grow
* 증가비율(flex-grow) 감소비율(flex-shrink) 기본비율 (flex-basis) 
* 플렉스 아이템에 적용.
* 아이템의 증가, 감소, 기본 비율을 설정하는 단축 속성

### flex-grow: 0; 
	숫자가 클수록 더 큰 영역을 가짐. 가변값이 아니거나 0인 경우 적용되지 않음. 0,1
### flex-shrink: 1; 
	숫자가 클수록 더 큰 영역이 감소. 가변갑이 아니거나 0인 경우 적용되지 않음.
### flex-basis:auto; 기본 너비 값 설정.  
	auto인 경우 width, height등의 속성으로 너비 설정 가능하나 단위값이 주어진 경우 설정할 수 없음.