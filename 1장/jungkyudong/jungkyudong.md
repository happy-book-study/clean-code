### 1.깨끗한 코드

### 좋은코드 vs 나쁜코드
* 안돌아가는 프로그램보다 돌아가는 쓰레기가 낫다.....?
#얽히고설킨코드 #해독 #생산성

*일정과 요구사항을 강력하게 밀어붙이는 이유는 그것이 그들의 책임이기 때문이다.*
*좋은 코드를 사수하는 일은 바로 우리 프로그래머들의 책임이다.*

*나쁜 코드의 위험을 이해하지 못하는 관리자의 말을 그대로 따르는 행동의 전문가답지 못하다.*

-------

### 좋은코드 = 깨끗한코드
* 논리가 간단
	* 메소드를 예로 설명한다면, if안에 if 또 그안에 if 등 사용하고자 하면 코드를 뜯어보고 여러 조건을 머리속에 암기해야 사용할 수 있는 불편한 코드가 아닐까 생각한다. 
* 의존성 최소
	* 변경엔 닫혀있고, 확장엔 열려있도록!
	* 제어의 역전
	*  테스트에도 용이하다! (TDD)
* 성능 최적화
* 오류 처리
	* 일반적으로 DB에 데이터를 저장해야하며, 데이터의 일관성을 유지해야한다. 또, 클라이언트는 항상 개발자가 생각한대로 프로그램을 사용하지 않는다. (개발자의 실수 또는 버그 이지만..) 그로인해 프로그램에 이슈가 가지 않도록 해야한다. (Exception, Error)
* 한가지에 '집중'
* 읽기 쉬운 코드
	* 읽기 쉬운 코드는 고치기 쉬운 코드이고, 내 프로그램에 신경을 쓴 개발자이다. 
* 고치기 쉬운 코드
* 주의 깊게 작성한 코드
* 중복 줄이기
	* 첫째로 재사용 가능한 프로그램을 만들어야하며, 다른 개발자가 만들어 놓은 재사용 가능한 소스를 찾아봐야한다.
	* 메소드 추출, 상속 등
* 의미있는 이름
	* 의미있는 이름만으로도 어떤 도메인인지 사용법이 어떻게 되는지 유추할 수 있다.
* 기능을 기술하는 메소드 하나와 기능을 실제로 수행하는 메소드 여러개
	* 추상화와 인터페이스를 말하는 것이라고 생각된다.
* 초반부터 간단한 추상화 고려
