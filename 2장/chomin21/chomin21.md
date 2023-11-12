- 의도가 분명하게 이름 짓기
    - 코드 이해와 변경이 쉬워짐
    
    ```java
    int d; // 의도 분명X
    
    int daysSinceCreation; //의도 분명O
    ```
    

- 코드에 그릇된 정보를 남기지 말기
    - 다르게 해석될 수 있는 단어 사용하지 않기
        
        ex) hp, ~List, ~Group
        
    - 서로 흡사한 이름 사용하지 않기
        
        차이를 단번에 파악하기 힘듦
        
    - 일관성이 떨어지는 표기법 사용 X
        
        유사한 개념은 유사한 표기법을 사용해야 함
        
- 의미 있게 구분하기
    - 의미없는 연속된 숫자, 불용어를 추가하는 것은 적절하지 못함.
        
        ex) list1, list2 ,,,   → 연속된 숫자
        
        ProductInfo vs ProductData → 불용어
        
    - 읽는 사람이 차이를 알도록 이름을 지어야 함

- 발음하기 쉬운 이름 사용하기
    - 다른 사람과 의사소통하기 어려움.
    
- 검색하기 쉬운 이름 사용하기
    - 문자 1개로 이름을 지우면 검색이 어려움
    - 상수보다 변수로 선언해서 사용하는 것이 좋음
        
        ex) 7을 검색하는 것보다 const int DAYS_PER_WEEK = 7; 로 선언되어있는 변수를 찾는 것이 더 쉬움. 
        
    - 이름 길이는 범위 크기에 비례해야 함

- 인코딩 피하기
    - 인터페이스 이름에 I(대문자) 사용 금지
        
        ex) IShapeFactory (X), ShapeFactoryImpl (O)
        
    - 멤버 변수에 접두어 사용 금지
        
        ex) String m_dsc (X)
        
- 문자 하나만 사용하는 변수 이름 사용 X
    - 루프에서 반복 횟수를 세는 변수 i, j, k는 괜찮음
    
- 클래스 이름
    - 명사, 명사구 O
        
        ex) Customer, WikiPage, Account, AddressParser
        
    - 단어, 동사 X
        
        ex) Manager, Data, Info
        
- 메서드 이름
    - 동사, 동사구 O
        
        ex) deletePage, save
        
    - get, set, is
    - 생성자 중복 정의 시 인수를 설명하는 이름 사용.
        
        ex) new Complex(23.0)  (X)
        
        Complex.FromRealNumber(23.0) (O)
        
- 기발한 이름 사용 X

- 한 개념에 한 단어 사용
    - 똑같은 메서드를 클래스마다 .fetch, retrieve, get으로 제각각 부르는 것은 혼란스러움.
    
- 한 단어를 두가지 목적으로 사용 X
    
    ex) add를 두 숫자를 더하는 용도와 하나의 집합에 다른 요소를 추가하는 용도 2가지로 사용
    

- 해법 영역, 문제 영역에서 가져온 이름 사용하기

- 의미 있는 맥락 추가하기
    
    ex) firstName, lastName, state 보다는
    
    addrFirstName, addrLastName, addrState 가 더 명확함.
    
- 불필요한 맥락 없애기
    - 의미가 분명한 경우, 짧은 이름이 긴 이름보다 좋음.
    
    ex) GSD 회계 모듈이라고 해서 그 안의 변수에 모두 GSD를 붙이는 것은 바람직하지 않음.
    
    accountAddress 라는 변수가 있을 때, 다른 고객 관리 프로그램에서 GSD가 아닐 수 있음.
