# Servlet

* 웹 프로그래밍에서 Client의 요청을 처리하고 결과를 Client에게 전송하는 기술이다. <br>
  JAVA를 이용하여 Web을 만들기 위해서 필요한 기술이다.
* Client의 요청에 대해 동적으로 작동한다.
* HTML을 사용하여 요청에 응답한다.
* JAVA Thread를 이용하여 동작한다.
* MVC패턴에서 Controller로 이용된다.

1. 스프링에선 서블릿을 Dispatcher Servlet을 이용한다. Distpatcher Servlet은 Front Controller를 담당하며 모든 HTTP 요청을 받아들여 다른 객체들 사이의 흐름을 제어한다.<br>
   서블릿 요청에 관련된 객체를 정의하는 곳이 servlet-context.xml이 된다. 즉, 컨트롤러나 어노테이션, 뷰 리졸버 등을 설정해준다.
2. Servlet 별칭을 통해 Dispatcher Servlet을 매핑해준다. Url-Pattern을 '/' 설정하였기에 Root 경로로 들어온 모든 요청을 처리할 수 있게된다.
3. 모든 Servlet 및 Filter가 공유하는 Root Spring Container를 정의한다. Context configLocation 이라는 파라미터를 이용함으로써 contextLoader가 호출할 수 있는
   설정파일을 여러개 쓸 수 있다. 여기서 사용되는 xml은 root-xontext.xml로 Root context를 구성한다. 주로 Service나 Repository(Dao),DB 등 비즈니스 로직과 관련된 설정을 해준다.
4. 모든 Servlet 및 Filter가 공유하는 Spring Container를 생성한다.

* 웹 표준 개발 스펙(스프링 권장)
---> MVC패턴 + single tone 패턴 + Ajax + myBatis + HTML5 + CSS(BootStrab) + java script
