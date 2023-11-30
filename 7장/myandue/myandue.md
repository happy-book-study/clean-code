### 7장.  오류 처리

- 이 파트도 조금 이해가 어려웠다. 오류 코드 말고 예외를 사용하라는게 뭔가 오류를 너무 특정짓지 말라고 얘기하는것 같은데, 예외도 구체적인 예외를 잡는단 말이지..?(ex. Exception 말고 FileNotFoundException)
- 그리고 뭔가 내가 실행하기가 어려워 보인다..
- **Try-Catch-Finally 문부터 작성하라**
    - 어떤 기능을 구현할 때, 해당 기능에 예상되는 예외를 예측으로 두는 Test 문(`@Test(expected = StorageException.class`)을 작성하고,  구현하려던 코드에서 예외를 먼저 던져볼 수 있도록 구현해본다.
    - 예외를 던짐으로써 테스트가 성공하면 이제 나머지 논리들을 추가한다. 나머지 논리에서는 오류나 예외가 발생하지 않는다고 가정한다.
    - 해당 행위는 try-catch 블록을 통해 트랜잭션을 유지할 수 있도록 하기 위함이다.
- **미확인 예외를 사용하라**
    - 이 부분 아예 이해가 안됐다 ㅠㅠ
    - 선언부에 정의된 예외를 ‘확인된 예외’ 라고 하는 것 같은데,, 오류 코드 정의랑 다른걸까,,?
- **예외에 의미를 제공하라**
    - 예외를 던질 때는 전후 상황을 충분히 덧붙인다.
    - 안그래도 요새 예외 처리에 대해 고민이 많았는데 나름 근래에 혼자 생각해서 실행했던 방안이었다.
    - 특히 라이브러리를 이용해서 처리할 때, 라이브러리는 try-catch 블럭을 이용해 사용하고 해당 catch 문에서 throw new Error(error) 를 할 때 어느 라이브러리 사용 때 발생한 에러인지 내용을 붙여줬다.
        - `throw new Error(`AXIOS ERROR: ${error.message}`)`
- **정상 흐름을 정의하라**
    - 실상 논리적으로? 정상적으로? 구현할 수 있는 부분을 예외처리를 이용해 처리하지 말라는 것 같다. 예시가 이해하기 쉽다.
    
    ```java
    try {
    	MealExpenses expenses = expenseReportDAO.getMeals(employee.getId());
    	m_total += expenses.getTotal();
    } catch(MealExpensesNotFound e) {
    	m_total += getMealPerDiem();
    }
    ```
    
    ⇒ employee의 아이디로 getMeals를 했을 때 값이 나오면(식비를 청구했다면) 해당 값을 총계에 더하고 없다면 getMealPerDiem() 값(일일 기본 식비) 을 총계에 더하는 로직이다. 
    
    ⇒ ‘없다면’을 굳이 예외처리로 잡아내야할까?
    
    ```java
    MealExpenses expenses = expenseReportDAO.getMeals(employee.getID());
    m_total += expense.getTotal();
    ```
    
    ⇒ 그냥 위와 같이 구현할 수 있다. getMeals() 에서 이미 원하던 처리를 해낼 수 있다.
    
    ```java
    public class PerDiemMealExpenses implements MealExpenses {
    	public int getTotal() {
    		// 기본값으로 일일 기본 식비를 반환한다. 
    	}
    }
    ```
    
    ⇒ 이를 특수 사례 패턴(SPECIAL CASE PATTERN)이라 부른다고 한다. 클래스를 만들거나 객체를 조작해 특수 사례를 처리하는 방식이다. 
    
- **null을 반환하지 마라**
- **null을 전달하지 마라**
    - null이 없을 수는 없을테고(데이터가 존재하지 않을 수 있으니까), 해당건을 최대한 하위에서 해결해야하는 것같다. 그렇지 않으면 null을 계속 상단으로 전달해야할테고, 그럼 계속해서 null에 대한 처리를 해야할테니까.
    - 그리고 인수로 null 전달을 하지 않도록 정책적으로 정해놓으라고 한다.
