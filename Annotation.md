# 어노테이션

### @RequestBody
* Http 요청의 Body 내용을 Java Object로 변환시켜주는 역할을 한다. ※Java Object --> Json이나 XML형식들의 데이터를 Jackson등의 메세지 컨버터를 활용하여 변환시켜준다.
  그렇기 때문에 Body가 존재하지 않는 "GET" 방식의 메소드에는 적합하지 않다. --> 에러발생
  즉, @RequestBody는 반드시 __"POST"__ 요청과 함께 사용되어야 한다.
* 데이터를 변환해주는 성질은 파라미터로 받은 데이터들을 자바객체로 1:1로 매칭시켜주는 @ModelAttribute 와는 차이가 있다.
- 정리 : @RequestBody는 POST방식으로 JSON 형태로 넘겨온 데이터를 객체로 바인딩하기 위해 사용할 수 있다.
