###6.객체와 자료 구조
### 자료 추상화
구현을 외부로 노출 or 숨김 (= 인터페이스)
### 자료/객체 비대칭
- 자료 구조 : 자료를 그대로 공개하며 별다른 함수는 제공하지 않음
	- 자료 구조를 사용하는 절차적인 코드는 기존 자료 구조를 변경하지 않으면서 새 함수를 추가하기 쉽다.
	- 새로운 자료구조는 추가하기 어렵다.
~~~JAVA
public class Square {
	public Point topLeft;
	public double side;
}

public class Rectangle {
	public Point topLeft;
	public double height;
	public double width;
}

public class Circle {
	public Point center;
	public double radius
}

public class Geometry {
	public final double PI = 3.14159265;

	public double area(Object shape) throws NoSuchShapeException
	{
		if(shape instanceof Square) {
			Square s = (Square) shape;
			return s.side * s.side;
		}
		else if(shape instanceof Rectangle) {
			Rectangle r = (Rectangle) shape;
			return r.height * r.width;
		}
		else if(shape instanceof Circle) {
			Circle c = (Circle) shape;
			return PI * c.radius * c.radius;
		}

		throw new NoSuchShapeException();
	}
}
~~~

- 객체 : 추상화 뒤로 자료를 숨긴 채 자료를 다루는 함수만 공개
	- 기존 함수를 변경하지 않으면서 새 클래스를 추가하기 쉽다.
	- 새로운 함수를 추가하기 어렵다. 그러려면 모든 클래스에 추가해줘야 한다.
~~~JAVA
public class Square implements Shape {
	private Point topLeft;
	private double side;

	public double area() {
		return side * side;
	}
}

public class Rectangle implements Shape {
	private Point topLeft;
	private double height;
	private double width;

	private double area() {
		return height * width;
	}
}

public calss Circle implements Shape {
	private Point center;
	private double radius;
	public final double PI = PI = 3.14159265;

	public double area() {
		return PI * radius * radius;
	}
}
~~~
**새로운 자료 타입이 필요한 경우 - 클래스와 객체 지향 기법이 적합하다.** 
**새로운 함수가 필요한 경우 - 절차적인 코드와 자료 구조가 적합하다.**

### 디미터 법칙
---

어떤 객체가 다른 객체에 대해 지나치게 많이 알다보니, 결합도가 높아지고 좋지 못한 설계를 야기한다는 것을 발견하였다. 그래서 이를 개선하고자 객체에게 자료를 숨기는 대신 함수를 공개하도록 하였는데, 이것이 바로 디미터의 법칙이다.

즉, 디미터의 법칙은 다른 객체가 어떠한 자료를 갖고 있는지 속사정을 몰라야 한다는 것을 의미하며, 이러한 이유로 Don’t Talk to Strangers(낯선 이에게 말하지 마라) 또는 Principle of least knowledge(최소 지식 원칙) 으로도 알려져 있다.

출처: [https://mangkyu.tistory.com/147](https://mangkyu.tistory.com/147) [MangKyu's Diary:티스토리]

~~~JAVA
public class App { 
	public static void main(String[] args) {
		final Address address = new Address("종로구 청와대로 1", 03054, "서울특별시");
		final Enterprise enterprise = new Enterprise(100, "청와대", address);
		final Employee employee = new Employee("안주형", enterprise);
		//1번 - 디미터 법칙 위반 코드!!
		System.out.println(employee.getEnterprise()
								.getAddress()
								.getPostalCode()); 
		
		// 2번 - 디미터 법칙 준수 코드!!
		System.out.println(employee.getEnterprisePostalCode()); 
	} 
}
 ~~~
 - 예외사항
	- DTO나 컬렉션 객체와 같은 자료 구조의 경우에는 물을 수 밖에 없다. 만약 묻는 대상이 객체가 아닌 자료구조라면 당연히 내부를 노출해야 하므로 디미터의 법칙을 적용할 필요가 없다.

~~~JAVA
final String outputDir = ctxt.getOptions()
							.getScratchDir()
							.getAbsolutePath();

final String outputDir = ctxt.options.scratchDir.absolutePath;
~~~

### 잡종구조
...

### 구조체 감추기
위의 코드와 같이 outputDir을 가져오는 코드를 살펴보고, 그 행위를 ctxt에 메소드 구현
~~~JAVA
BufferedOutputStream bos =        ctxt.createScratchFileStream(classFileName);
~~~

### 자료 전달 객체
- 자료 구조체의 전형적인 형태는 공개 변수만 있고 함수가 없는 클래스이다. (= DTO)

### 활성화 레코드
...