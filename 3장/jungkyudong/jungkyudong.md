3. 함수

### 작게 만들어라!

- 얼마나 짧아야 되지? 3줄,4줄

~~~
public static String rederPageWithSetupsAndTeardowns(PageData pageData, boolean isSuite) throws Exception {
	if(isTestPage(pageData))
		includeSetupAndTeardownPages(pageData, isSuite);
	return pageData.getHtml();	
}
~~~

#### 블록과 들여쓰기
- if문 else문 while문 등에 들어가는 블록은 한 줄이어야 한다!
- 들여쓰기 수준은 1단이나 2단을 넘어서면 안된다!

#### 한 가지만 해라!
*'한 가지'가 무엇인가?????????????*
1. 페이지가 테스트 페이지인지 판단한다.
2. 그렇다면 설정 페이지와 해제 페이지를 넣는다.
3. 페이지를 HTML로 랜더링한다.

한 가지만 하는가? '추상화 수준'이 하나다.
??? 더 이상 쪼개면 의미가 사라지는 수준...

#### 함수 당 추상화 수준은 하나로!

### Switch문
- switch문을 사용해 클래스의 인스턴스를 생성하고 추상 클래스를 리턴, 팩토리성으로
- 해당 클래스에서 각자의 함수 구현, 추상클래스에서 메소드 정의

### 함수 인수
1. 인수 개수는 적어야한다.
	- 삼항은 가능한 피하는 편이 좋다.
2. 인수는 input
3. 플래그 인수는 추하다.
4. 클래스로 넘기는것은 인수를 줄이는 방법일 뿐 아니라, 개념을 표현해준다
	- double x, double y -> Point center

### 동사와 키워드
wrinte(name) >> writeField(name)
assertEquals() >> assertExpectedEqualsActual(expected, actual)

### 부수효과를 일으키지마라
	checkPassword() 에서 세션을 초기화 하는 경우, 사용자가 메소드명을 보고 판단이 안된다.
	checkPasswordAndInitializeSession이라는 이름이 훨씬 좋다.
	'한 가지'만 한다는 규칙을 위반하지만.

### 출력 인수
- 우리는 인수를 함수 입력으로 해석한다.

### 명령과 조회를 분리하라!
객체 상태를 변경하거나, 객체 정보를 반환하거나 둘 중 하나만 해야 한다.
1. 필드가 있는지 찾는다.
2. 있으면 세팅한다. 그리고 true 리턴
3. 없으면 false 리턴
- 찾는 메소드와, 세팅하는 메소드를 구분해서 구현한다.
### 오류 코드보다 예외를 사용하라!
- 예외를 사용하면 Try/Catch로 잡아주면 되서 깔끔해진다.

#### 오류 처리도 한 가지 작업이다.

#### 모든 함수와 함수 내 모든 블록에 입구와 출구가 하나만 존재해야 한다.
- return문이 하나여야 한다.
- 루프 안에서 break나 continue를 사용해선 안 된다.

