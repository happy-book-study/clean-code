### 5장. 형식 맞추기

- **적절한 행 길이를 유지하라**
    - **신문 기사처럼 작성하라**
        - 우선 이름을 통해 내가 원하는 모듈인지를 확인할 수 있을 정도로 이름을 간단하고 설명 가능하게 짓는다.
        - 소스 파일 첫 부분은 고차원 개념과 알고리즘을 설명한다.
        - 아래로 내려갈수록 의도를 세세하게 묘사한다.
    - **개념은 빈 행으로 분리하라**
        - 일련의 행 묶음은 완결된 생각 하나를 표현한다.
        - 생각 사이에는 빈 행을 넣어 분리해야 한다.
        - 나 같은 경우, import 를 할 때에도 library, model, service 호출 묶음 사이를 빈 행으로 분리한다.
    - **세로 밀집도**
        - 유사한 성격의 묶음은 가까이 두어야지 그 사이를 의미없는 다른 무언가로 채우면 가독성이 떨어진다.
    - **수직 거리**
        - **변수 선언**은 해당 변수를 사용하기 바로 전에 선언한다.
        - **인스턴스 변수**는 클래스 맨 처음에 선언한다.
        - **종속 함수**
            - 한 함수가 다른 함수를 호출한다면 두 함수는 세로로 가까이 배치한다.
            - 호출하는 함수를 호출되는 함수보다 먼저 배치한다.
            - 이 부분(함수 배치)이 은근 어려운데, 내가 작성하고 있는 함수가 어떤것을 save하면 그것을 이용해 calculate 하는 함수를 호출한다. 그래서 save 함수 다음 calculate 함수를 배치시켰는데, update할 때에도 calculate 함수를 호출한다. 이 때에 ‘save → update → calculate’ 순으로 배치시켜야할지 ‘save → calculate → update’ 로 배치시켜야할지 모르겠더라,,
            - 종속의 깊이? 로 봤을 때 전자가 맞으려나 싶기도 하고..
- **가로 형식 맞추기**
    - 개인적으로, 가로 길이를 너무 늘이지 않게 행 분리를 하는것도 좋지만 무분별하게 행 분리가 이루어지는 것도 참 싫어한다.
    - 예를들어,
        
        ```jsx
        if ((iAmByunsu === '123') &&& (youAreByunsu === '456')) {
        	///
        }
        ```
        
        이렇게 돼있을 때, 저 조건절이 길다고 치면 아래정도는 괜찮다.
        
        ```jsx
        if ((iAmByunsu === '123') 
        	&&& (youAreByunsu === '456')) {
        	///
        }
        ```
        
        근데 내 기준 아래는 넘 과하다.
        
        ```jsx
        if (
        (iAmByunsu === '123') 
        	&&& (youAreByunsu === '456')
        ) {
        	///
        }
        ```
        
        개인적으로 저렇게 과하게 행분리하면 더 눈에 안들어온다고 생각한다.
        
- **밥 아저씨의 형식 규칙**
    - 저자의 코드 규칙이 담긴 예시가 있는데, 내 취향으로는 여기에 더해서 if 문 내부 내용은 무조건 다 대괄호 안에 넣어주는 것이다.
        
        ```java
        private static void findJavaFiles(File parentdirectory, List<File> files) {
        	for (File file : parentDirctory.listFiles()) {
        		if (file.getName().endsWith(".java"))
        			files.add(file);
        		else if (file.isDirectory())
        			findJavaFiles(file, files);
        	}
        }
        ```
        
        if 문 보면 들여쓰기 및 세미콜론으로 충분히 분간이 되긴하는데 진짜 그냥 내 취향,, 
        
        ```java
        private static void findJavaFiles(File parentdirectory, List<File> files) {
        	for (File file : parentDirctory.listFiles()) {
        		if (file.getName().endsWith(".java")) {
        			files.add(file);
        		}	else if (file.isDirectory()) {
        			findJavaFiles(file, files);
        		}
        	}
        }
        ```
