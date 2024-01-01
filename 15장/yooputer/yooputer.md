# 15장 JUnit 들여다보기

### JUnit 프레임워크
- 켄트 백과 에릭 감마가 비행기 안에서 3시간동안 기초를 구현한 프레임워크

### ComparisonCompactor 모듈 테스트케이스
- ex)
```
public failure = new ComparisonCompactor(0, "b", "c").compact("a");
assertTrue("a expected:<[b]> but was:<[c]>".equals(failure));
```
- ComparisonCompactor 모듈을 써본적이 없어서 이해가 잘 안됐다

### 디팩터링하는 법!
- 변수, 메서드, 클래스의 의미를 전혀 모르게 만들기!
- 불필요한 코드 추가하기!
- 메서드 뭉쳐놓기!
- 일관성 박살내기!
- 메서드의 파라미터를 여러개 받아서 헷갈리게 만들기!
- 중복코드 남발하기!
