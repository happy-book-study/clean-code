### 9. 단위테스트
### TDD 법칙 세 가지
~~~
1. 테스트 케이스 먼저 작성
2. 테스트 케이스에 맞게 개발 진행(쓰레기 코드라도)
3. 테스트 진행
4. 피드백 및 추가 구현, 리팩토링
5. 반복
~~~
- 첫째 법칙 : 실패하는 단위 테스트를 작성할 때까지 실제 코드를 작성하지 않는다.
- 둘째 법칙 : 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다.
- 셋째 법칙 : 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다.
**잘 작성한 테스트코드는 테스트 문서 대체 가능**
### 깨끗한 테스트 코드
- BUILD-OPERATE-CHECK 패턴
- GIVEN-WHEN-THEN 패턴
~~~
단위 테스트 시 중요한 건, 테스트할 적당한 값을 찾는 것이다. 무작정 아무 값이나 테스트하는 것이 아니라는 점이다. 1~100까지의 100개의 테스트를 진행하는 것보다, **경계값에 대해서** 테스트를 진행해주는 것이 더 좋다.
~~~

### F.I.R.S.T
- Fast : 빨라야한다.
- Independent : 테스트는 서로 의존하면 안 된다.
- Repeatable : 어떤 환경에서도 반복 가능해야 한다.
- Self-Validating : 테스트는 Boolean값으로 결과를 내야 한다.
- Timly : 실제 코드를 구현하기 전에 테스트 코드를 구현한다.