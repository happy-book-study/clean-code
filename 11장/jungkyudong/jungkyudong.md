### 11. 시스템
### 도시
- 적절한 추상화와 모듈화

### 시스템 제작과 시스템 사용을 분리하라
- 애플리케이션 객체를 제작하고 의존성을 서로 '연결'하는 준비 과정과 준비 과정 이후에 이어지는 런타임 로직을 분리해야 한다.
- 관심사의 분리
	- 관심이 같은 것 끼리 모으고, 관심이 다른 것끼리 떨어뜨려놓는것

### 횡단 관심사
- AOP 프레임워크는 대상 코드에 영향을 미치지 않는 상태로 동작 방식을 변경한다.

### 자바 프록시
- 프록시 : 실제 비즈니스 로직과 그 외의 코드를 분리시키는 역할을 수행하는 객체를 만드는 패턴이다.
	- 실제로 로직을 수행하는 객체의 인터페이스 역할을 하게된다. 
	- 객체를 호출하는 지점에서 프록시 객체를 호출하여 부가적인 코드를 수행한 뒤 참조 변수를 통해 실제 서비스 객체를  호출한다.
~~~
jdk.proxy2.$Proxy11
대상클래스$$EnhancerByCGLIB$${랜덤코드}

데코레이트 패턴 : 
InputStream is = new BufferedInputStream(new FileInputStream("a.txt"));
~~~