### 5.형식 맞추기
#### 어떤 형식들이 있을 수 있을까?
- 괄호의 위치
~~~
#K&R
if(a == 1) {
	if(b == 1) {
		//TODO
	}
}
~~~
~~~
#BSD
if(a == 1)
{
	if(b == 1)
	{
	 //TODO
	}
}
~~~

- 변수/함수 표기법
	- 카멜케이스 : camelCase
	- 파스칼케이스 : PascalCase
	- 스네이크케이스 : snake_case
	- 메크로케이스 : SCREAMING_SNAKE_CASE
	- 케밥케이스 : kebab-case
	- 헝가리안케이스 : strName, iAmt
- 들여쓰기
	- 탭
	- 스페이스 : 2번, 4번
	- 
- 코드 컨벤션을 지키자
- 프로젝트 구조
- 주석 규칙 등

- 규칙을 자동으로 적용하는 도구
	- Prettier & ESLint
	- IDE 
		- https://anywaydevlog.tistory.com/110 구글 자바 컨벤션 적용
		- https://bestinu.tistory.com/64 네이버 자바 컨벤션 적용
**참고 사이트**
[https://google.github.io/styleguide/javaguide.html](https://google.github.io/styleguide/javaguide.html) 구글 자바 컨벤션 가이드  
[https://naver.github.io/hackday-conventions-java/](https://naver.github.io/hackday-conventions-java/) 네이버 자바 컨벤션 가이드

### 형식을 맞추는 목적
- 코드 형식은 의사소통의 일환이다.
- 오늘 구현한 코드의 가독성은 앞으로 바뀔 코드의 품질에 지대한 영향을 미친다.

protected 변수를 피해야 하는 이유

