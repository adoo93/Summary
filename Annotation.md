# 어노테이션

### @RequestBody
* Http 요청의 Body 내용을 Java Object로 변환시켜주는 역할을 한다. ※Java Object --> Json이나 XML형식들의 데이터를 Jackson등의 메세지 컨버터를 활용하여 변환시켜준다.
  그렇기 때문에 Body가 존재하지 않는 "GET" 방식의 메소드에는 적합하지 않다. --> 에러발생
  즉, @RequestBody는 반드시 __"POST"__ 요청과 함께 사용되어야 한다.
* 데이터를 변환해주는 성질은 파라미터로 받은 데이터들을 자바객체로 1:1로 매칭시켜주는 @ModelAttribute 와는 차이가 있다.
* 정리 : @RequestBody는 POST방식으로 JSON 형태로 넘겨온 데이터를 객체로 바인딩하기 위해 사용할 수 있다.

### @ModelAttribute
* 클라이언트가 전송하는 여러 파라미터들을 1:1로 객체에 바인딩하여 다시 view로 넘겨서 출력하기 위해 사용되는 오브젝트이다.
* 매핑시키는 파라미터의 타입이 객체의 타입과 일치하는지를 포함한 다양한 검증작업이 추가로 진행된다.
* 여러개의 파라미터를 바로 자바 빈 객체로 매핑시킨다.(RequestBody와 차이 비교)
* @ModelAttribute는 JSP에서 Form태그를 통해 전달받은 파라미터를 객체로 바인딩 하는 경우에 사용할 수 있다.

### @RequestParam
* 요청 파라미터를 메소드에서 1:1로 받기 위해서 사용한다. 사용하려면 기본적으로 반드시 해당 파라미터가 전송되어야 한다.
* 즉, 반드시 필요한 파라미터인가?를 나타내는 required의 값이 default로 true로 되어있어서 해당 파라미터가 전송되지 않으면 400에러를 유발할 수 있다.
* 반드시 필요한 변수가 아니면 required를 false로, 해당 파라미터를 사용 안 한다는 요청을 보내면 default로 받을 값을 설정한다.


## GET 방식과 POST 방식의 차이

### GET 방식
* 모든 파라미터를 URL을 통해서 직접 전달한다.
* 가시적인 보안에도 좋지 않고 보낼 수 있는 데이터의 양에도 한계가 있다.
* HTTP 프로토콜의 default방식은 GET 방식이다.

### POST 방식
* 전달하려는 정보가 HTTP Body에 포함되어 전달된다.
* 웹 브라우저 사용자의 눈에 보이지 않아서 보안적인 측면에서는 GET방식보다 좋다.
* 보낼 수 있는 양의 제한이 없다.
* 정보를 다 입력 후 제출 버튼을 누르면 Body에 값들이 포함되어져서 보내진다.

## 간단한 차이점
* GET은 URL에 '?' 라는 문자 뒤에 값이 쌍으로 붙고 POST는 body 태그 안에 숨겨져 보내진다.
* GET방식은 URL에 값이 따라 붙기 때문에 길이 제한에 있어서 많은 양의 데이터를 보내긴 어렵고 POST방식은 많은 양의 데이터를 보내기에 적합하다.

* SELECT 방식을 원한다면 GET, UPDATE방식을 원한다면 POST.
* GET은 캐시가 남아있어 전송속도가 빠르고 POST는 캐시가 남아있지 않아 보안적인면에서 유리하다.
* GET은 브라우저 히스토리에 파라미터가 남고, POST는 저장되지 않는다.