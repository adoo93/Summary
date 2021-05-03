# 자바스크립트 함수

### .replace()
* 특정 문자를 다른 문자로 치환해준다.
* 문법 : str_text.replace("찾을문자열","변경할 문자열");
  ex) var test = "가나다라 마바사 가나";
  var result = test.replace("가","나");
  console.log(result);
  결과 --> 나나다라 마바사 가나
  
### .split()
* 문자열을 분할하는 메서드
* 문법 : str.split("분할의기준",최대분할개수);
  ex)var str = "apple,banana,orange";
  var arr = str.str.split(",",2);
  document.writeln(arr[0]);
  document.writeln(arr[1]);
  document.writeln(arr[2]);
  결과 --> apple banana undefined
  
### .splice()
* 배열(Array) 객체에서 제공되는 함수, 원하는 위치에 요소를 추가하거나 삭제.
* 문법 : array.splice(start,count,[value],[value2] ... );
  ex) var mine = [0,1,2,3];
  mine.splice(2,0,5); --> 배열 2번째 위치한 곳에 숫자 5를 추가  // [0,1,5,2,3]
  mine.splice(2,0,5,7); --> 배열 2번째 위치한 곳에 숫자 5,7을 추가  //[0,1,5,7,2,3]
  mine.splice(1,1); --> 배열 1번째 부터 1개를 제거한다.          // [0,2,3]
  mine.splice(1,2); --> 배열 1번째 부터 2개를 제거한다.          // [0,3]
  mine.splice(1,1,5); --> 배열 1번째 부터 1개를 제거하고 5를 추가한다.  // [0,5,2,3]
  mine.splice(1,2,5); --> 배열 1번째 부터 2개를 제거하고 5를 추가한다.  // [0,5,3]
  var remove = mine.splice(1,1); --> 배열 1번째 부터 1개 제거한다.     // [1]
  var remove = mine.splice(1,2); --> 배열 1번째 부터 2개 제거한다.     // [1,2]
  
### .push()
* 배열의 끝에 요소 추가
* ex) var arr = ['a','b','c'];
  arr.push('d');    // arr = ['d','a','b','c']
  
### .unshift()
* 배열의 앞쪽에 요소 추가
* ex) arr.unshift('d');   // arr = ['b','c','e','f']

### .pop()
* 배열의 마지막 요소 제거
* ex) var arr = ['a','b','c','e','f']
  arr.pop();    // arr = ['a','b','c','e']
  
### .shift()
* 배열의 첫번재 요소 제거
* ex) var arr = ['a','b','c','e','f'];
  arr.shift();  // arr = ['b','c','e','f']
  
### .attr()
* 일반적인 태그 속성의 값을 변경할 때 사용
* HTML의 속성을 취급(HTML Element에 있는 정보)
* HTML attribute 값이 모두 String으로 넘어온다.
* ex) class 변경 -> $(":checkbox").attr("class","Large_checkbox");

### .prop()
* 태그 속성에 따라서 기능이 제어되는 속성 변경시 사용
* JavaScript의 프로퍼티를 취급.
* boolean,date,function 등의 데이터타입이 그대로 넘어옴.
* attr()에 비해 실행속도가 약 2.5배 빠르다.
* ex) 1.checkbox 상태 변경 --> $(":checkbox").porp("checked",true);
     
      2.combobox disabled 속성의 true,false 상태 변경 --> $("#combobox").prop('disabled',true);

* attr()은 요소의 현재 html의 원래 값을 제공하므로 javascript,jquery를 통해 수정된 요소의 값을 가져와야 할때는 prop()를 사용하는 것이 좋다.

### .append()
* 컨텐츠를 선택된 요소 내부의 끝 부분에서 삽입
* ex) $("testDiv").append('<div id="insertDiv"></div>');
      --> <div id="testDiv"><div id="..."></div><div id="insertDiv"></div></div>
      
### .prepend()
* 컨텐츠를 선택된 요소 내부의 시작부분에서 삽입
* 문법은 .append() 와 동일.
* ex) 결과 ---> <div id="testDiv"><div id="insertDiv"></div><div id="..."></div></div>

### .after()
* 선택한 요소 뒤에 컨텐츠 삽입
* 문법 동일
* ex) 결과 ---> <div id="testDiv"><div id="..."></div></div><div id="insertDiv"></div>

### .before()
* 선택한 요소 앞에 컨텐츠 삽입
* 문법 동일
* ex) 결과 ---> <div id="insertDiv"></div><div id="testDiv"><div id="..."></div></div>

### .indexOf()
* 문자열에서 특정 문자의 위치를 찾기 위함
* 문법 : String.indexOf(searchValue,Position)
* searchValue : 필수 입력값, 찾을 문자열
* Position : optinal, 기본값은 0, String에서 searchValue를 찾기 시작할 위치
* indexOf 함수는 문자열(String)에서 특정 문자열(searchValue)를 찾고, 검색된 문자열이 '첫번째'로 나타나는 위치 index를 리턴한다.
* 찾는 문자열이 없으면 -1, 문자열을 찾을때 대소문자를 구분한다.
* ex) var str = "abab";
  str.indexOf('ab');  // 0  'ab'가 처음 나타나는 인덱스의 값을 리턴
  str.indexOf('ba');  // 1  'ba'가 처음 나타나는 인덱스의 값을 리턴
  str.indexOf('abc'); // -1 'abc'라는 문자열이 없으므로 숫자 -1을 리턴
  str.indexOf('AB');  // -1 대문자 'AB'라는 문자열이 없으므로 숫자 -1을 리턴
  
### 선택자
* id, class = html 태그의 id나 class 속성에 부여된 값은 css파일이나 <style>태그에서 선택자로서 역할을 수행 할 수 있다.
* name = 선택자로서 역할을 수행 할 수 없다. 요소의 역할에 대한 참조로써 지정할 속성이며 자바스크립트 코드에서도 참조 될 수 있는 속성이다.
* id --> $("#아이디 밸류")         __
  class --> $(".클래스밸류")       __ㅣ-->>>> Jquery에서   
  name --> $('[name="네임밸류"]')  __ㅣ
 
