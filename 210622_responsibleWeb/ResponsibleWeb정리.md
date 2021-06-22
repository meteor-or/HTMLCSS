# mediQueries
## 개념
* 화면 해상도, 기기 방향 등의 조건으로 html에 적용하는 스타일에 전환할 수 있는 CSS3의 속성 중 하나이다.
## 기본 작성 방식  
* @media [only 또는 not] [미디어유형] [and 혹은 ,] (조건문) {실행문}  
* 미디어유형:screen,all,print...
* @media screen and (조건값:min-width:415px) {실행문
		}
* **뷰포트 값은 필수!**   
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`
## 모바일 우선
* 모바일 우선 mobile fitst로 인해 min-width 조건 적용이 많아짐
* **** min을 사용할 땐 반드시 크기가 작은 순서대로 작성해야 하고 max를 사용할 때는 반드시 크기가 큰 순서대로 작성해야 한다.
### 모바일 우선 css
* 띄어쓰기 주의
1. **min-widht**
```
@media screen and (min-width:768px) {/* 스크린의 가로사이즈가 최소 1200px 이상이면 적용. ~타블렛 */
			body{background-color: teal;font-size: 1.2rem;}
			h1{background-color: orange;}
		}
		
		/* 스크린의 가로사이즈가 최소 1200px 이상이면 적용. */
		@media screen and (min-width:1200px) {
			body{background-color: #ddd; color:saddlebrown;}
			h1 {text-decoration: underline;}
			::selection {background-color: orange;}
		}
		/* 스크린의 가로사이즈가 최소 1680px 이상이면 적용. */
		@media screen and (min-width:1680px) {
			h1{
				padding:10px;
				font-size:1.6rem;
			}
			h2{
				border:6px groove #9df;
			}
			p {
				font-size: 1.1rem;
			}
			::selection{background-color: transparent;}
			
		}
```
2. **max-width**
```
		/* pc 스타일 */
		body {background-color: maroon; color: white; font-size: 1.6rem;}
		ul{margin: 50px;list-style: square; font-weight: bold; line-height: 1.6; color: gold;}
		
		/* 스크린의 가로 크기가 최대 1200px이하 일때 적용. 즉 최대 1200px까지 적용*/
		/* @media all and () {} */
		@media (max-width:1200px) {
			body{background-color: orange;}
			ul {color: #000; border:3px double #000}
		}
		/* 스크린의 가로 크기가 최대 768px이하 일때 적용. 즉 최대 768px까지 적용*/
		@media (max-width:768px) {
			body{background-color: lightblue; color:#000}
			h2{font-size:1.2rem;}
			ul{text-decoration:underline; font-size: 1.4rem; background-color: #fff;}
			
```
3.  max-width, min-width 둘 다 사용 (범위 지정)
```
	/* 모바일 우선 min-width */
		body{background-color: maroon;color:white; font-size: 2px solid #000; border-bottom: 1px solid #000;}
		h1{text-align: center; background-color: #fff; border-top: 1px solid #000; padding:10px}
		h2{ text-align: center; margin: 10px;}
		p{background-color: lightblue;}
	
	/* 768px ~1200px의 범위 외는 적용되지 않음 */
	@media screen and (min-width:768px) and (max-width:1200px) {
		body{background-color: orange;}
	}
		h1{background-color: pink;}
	
	@media screen and (min-width:1640px) and (max-width:1940px) {
		body { background-color: #ddd;}
	}
```
## 외부선언 방법
1. 
	`<link rel="stylesheet" href="mq_all.css">`
2.  
		
		`min-width 작성시 작은 값을 먼저 작성 
		<link rel="stylesheet" href="mq_m.css">
		<link rel="stylesheet" href="mq_t.css">
		<link rel="stylesheet" href="mq_pc.css"`
3. 
```
<link rel="stylesheet" href="mq_m.css">
<link rel="stylesheet" media="(min-width:768pxp)" href="tablet.css">
<link rel="stylesheet" media="(min-width:1280pxp)" href="pc.css">
```



