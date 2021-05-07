# MyBatis

## ${} 와 #{}의 차이
### #{}
* 파라미터가 String 형태로 들어와 자동적으로 '파라미터'가 된다. 예를 들어, #{userId}의 userId 값이 abc라면 쿼리문에는 USERID = 'abc'라는 형태가 된다.
* 쿼리 주입을 예방할 수 있어 보안측면에서 유리하다.

### ${}
* 파라미터가 바로 출력된다.
* 해당 컬럼의 자료형에 맞추어 파라미터의 자료형이 변경된다.
* 쿼리 주입을 예방할 수 없어 보안측면에서 불리하다. 그러므로, 사용자의 입력을 전달할때는 사용하지 않는 편이 낫다.
* 테이블이나 컬럼명을 파라미터로 전달하고 싶을 때 사용한다. #{}은 자동으로 "가 붙어서 이 경우에는 사용할 수 없다.

## ```<SELECT>``` 태그 속성
* ```<SELECT>``` 구분은 데이터를 조회 할 때 사용하는 구문이다. 이 태그 내에는 몇가지 속성 값들이 존재한다.

### 속성

|제목|설명|
|---|------|
|id|구문을 찾기 위한 유일한 구분자|
|parameterType|구문에 전달되는 파라메터의 alias나 풀 클래스명|
|resultType|구문의 결과를 받을 alias나 풀 클래스명|
|resultMap|resultType과 다르게 xml 내 선언해서 사용하는 커스텀 맵|
|flushCache|기본값은 false, true 설정 시 로컬 및 2nd 캐쉬가 삭제된다.|
|useCache|기본값은 true, 로컬 및 2nd 캐쉬 사용|
|timeout|최대 대기시간 설정, 드라이버에 따라 지원이 되지 않을 수 있음.|
|parameterMap|외부 파라미터 맵을 찾기 위한 접근방법. 비권장. parameterType 사용을 권장.|
* 보통의 경우 id와 resultType, parameterMap을 사용하고, 특수한 경우 위의 옵션들을 사용한다. <br>
  resultType, parameterType의 경우 클래스의 alias나 풀 패키지를 포함한 클래스명으로 설정하고, 변수의 기본형으로도 사용할 수 있다.
  
```<select id="getDate" resulttype="java.lang.String" parameterType="java.lang.String">```<br>
```SELECT id FROM MEMBER WHERE id = #{id}```<br> ```</select>```
* resultType은 SELECT 구문의 id값의 타입, parameterType은 매개변수로 전달되는 #{id}의 타입을 말한다.
