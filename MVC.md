# MVC

## MVC 각 컴포넌트의 역할 <Who, When, what>
### Controller(컨트롤러)
* 일종의 조정자라고 할 수 있다. 클라이언트의 요청을 받았을 때, 그 요청에 대해 실제 업무를 수행하는 모델 컴포넌트를 호출한다.<br>
  또한 클라이언트가 보낸 데이터가 있다면, 모델에 전달하기 쉽게 데이터를 가공한다. 모델이 업무를 마치면 그 결과를 뷰에 전달한다.

### Model(모델)
* 컨트롤러가 호출할 때, 요청에 맞는 역할을 수행한다. 비즈니스 로직을 구현하는 영역으로 응용프로그램에서 데이터를 처리하는 부분이다.<br>
  비즈니스 로직이란 업무에 필요한 데이터처리를 수행하는 응용프로그램의 일부라고 할 수 있다. DB에 연결하고 데이터를 추출하거나 저장,삭제,업데이트,변환 등의 작업을 수행한다.
  상태의 변화가 있을 때 컨트롤러와 뷰에 통보해 후속 조치 명령을 받을 수 있게한다.
  
### View(뷰)
* 컨트롤러로부터 받은 모델의 결과값을 가지고 사용자에게 출력할 화면을 만드는 일을 한다. 만들어진 화면을 웹 브라우저에 전송하여 웹브라우저가 출력하게 하는 것이다.
  화면에 표시되는 부분으로 추출한 데이터나 일반적인 텍스트 데이터를 표시하거나 입력 폼 또는 사용자와의 상호작용을 위한 인터페이스를 표시하는 영역이다.

## MVC 구동원리 <HOW>
![mvc](https://user-images.githubusercontent.com/72905696/117923095-718f0d00-b32e-11eb-8b19-a1558b900d07.png)
* *C/S(Client - Server) 구조로 요청을 하면 그에 맞는 응답을 하는 구조를 기본으로 하고있다.*
1. 웹 브라우저가 웹 서버에 웹 애플리케이션 실행을 요청한다. (MVC 구조가 WAS라고 보면 된다.)
2. 웹 서버는 듫어온 요청을 처리할 수 있는 서블릿을 찾아서 요청을 전달한다.(Matching)
3. 서블릿은 모델 자바 객체의 메서드를 호출한다.
4. 데이터를 가공하여 값 객체를 생성하거나, JDBC를 사용하여 데이터베이스와의 인터랙션을 통해 값 객체를 생성한다.
5. 업무 수행을 마친 결과값을 컨트롤러에게 반환한다.
6. 컨트롤러는 모델로부터 받은 결과값을 View에게 전달한다.
7. JSP는 전달받은 값을 참조하여 출력할 결과 화면을 만들고 컨트롤러에게 전달한다.
8. 뷰로부터 받은 화면을 웹 서버에게 전달한다.
9. 웹 브라우저는 웹 서버로부터 요청한 결과값을 응답 받으면 그 값을 화면에 출력한다.