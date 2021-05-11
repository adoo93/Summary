# JQGRID

## 소개
* jqGrid는 jQuery 라이브러리를 이용한 Grid Plugin이다. 
* jqGrid는 웹에서 테이블 형식의 데이터를 표시하고 조작을 위한 Ajax 기반 자바스크립트 컨트롤러이다.
* jqGrid는 기본적으로 jQuery-UI를 이용하기 때문에 원하는 테마를 만들어서 사용 가능하다.<br>
  즉, jqGrid는 Ajax가 내장되어 있어서 조금만 이해하고 공부한다면 쉽게 데이터를 화면에 뿌려줄 수 있지만, 반대로 jQuery 기반의<br> 
  플러그인이기 때문에 jQuery에 대한 기본적인 지식이 없다면 사용하기 어려울 것이다.<br> 
* jqGrid의 최고 장점 중의 하나는 페이징, 정렬과 같은 기능을 제공해주는 것이다.

### 동작원리
1. 먼저 클라이언트가 페이지를 서버에 요청한다.
2. 서버는 요청한 페이지를 응답할 것이고 페이지가 로드 된 후 스크립트를 호출한다.
3. 스크립트 내에 있는 그리드는 Ajax 통신으로 데이터를 가지고와서 html내에 있는 table에 그려주는 방식으로 동작한다.

## 환경설정
* jqGrid를 사용하기 위해서는 먼저 라이브러리를 다운 받아야 한다. 유의할 점은 script 선언 순서인데, jqGrid는 jQuery기반이기 때문에<br> 꼭 jquery를 jqGrid보다 먼저 선언하여야 한다.

## 옵션
* 우선 jqGrid를 그리기 위해서는 그리드를 그려줄 table이 필요하다. 선언한 테이블에 ID값을 주고 스크립트에서는 그 ID값에 그리드를 설정해주면 된다.
* 그리드를 그리기 위한 설정 시 기본 옵션들의 규칙은 "name : value"의 형태이다. 여기서 value값은 단순한 값일 수도 있지만, 함수일 수도 있다.<br>
  다음은 그리드의 많은 옵션들 중 중요한 옵션 몇가지이다.
  <br>
  |옵션 이름|역할|
  |---|-----|
  |url|데이터를 가지고 올 수 있는 주소를 입력한다.|
  |mtype|요청방식을 설정한다. GET/POST|
  |datatype|가지고 오는 데이터의 타입을 설정한다. 보통 xml,json,local 이렇게 세가지를 자주 사용한다.|
  |colNames|그리드 각각의 컬럼에 출력되는 이름이다. 배열로 설정한다.|
  |colModel|각 컬럼에 대한 상세 정보이다. 서버로부터 받아온 데이터를 매핑해서 출력한다.|
  |jsonReader/xmlReader|데이터 타입이 json/xml일 경우 reader를 통해서 데이터를 어떻게 읽어드릴지 설정한다.|
  |rowNum|초기에 출력할 데이터의 개수를 설정한다.|
  |pager|그리드의 대표기능인 페이저를 설정한다. 그리드 테이블 밑에 div를 넣어주고 그 div의 id값을 써주면 된다.|
  |multiselect|row마다 selectbox가 생긴다.|
  |postData|서버에 파라미터로 넘길 데이터를 설정한다. 배열의 형태로 설정 가능하다.|
  
## colModel 옵션
* jqGrid 옵션 중에서도 중요한 옵션이 여러가지 있지만, 가장 중요하다고 생각하는 옵션은 data와 직접 관련있는 colModel이라고 생각한다. <br>
  중요한 만큼 그리드에서도 colModel만을 위한 옵션들을 제공하고 있다. colModel의 기본적인 특징은 데이터를 매핑 해준다는 것이다. <br>
  매핑이 이뤄지는 방식은 colModel 옵션 중 하나인 "name"을 이용하여 이뤄진다. 이때 "name"의 value값을 데이터의 변수명과 일치시켜주면 자동으로 매핑된다.
  <br>
  |옵션|역할|
  |---|-----|
  |name|출력할 데이터의 이름이다. 서버에서 받은 데이터의 변수명을 명시해준다.|
  |index|컬럼 정렬 시 서버에 넘어가는 값이다. index값을 설정하지 않으면 name값이 넘어간다.|
  |width|컬럼의 넓이를 설정한다.|
  |align|컬럼 내 데이터의 정렬을 설정한다. (left, right, center 등)|
  |hidden|데이터값은 설정하고 화면에서 보이고 싶지 않을 때 사용한다.|
  |formatter|데이터로 들어온 값을 특정 형식으로 변환해서 보여줄 수 있다.|
  |sortablt|해당 컬럼이 정렬될 수 있는지를 지정. 일반적으로 true설정이며 특정 컬럼의 정렬을 허용하지 않을 때 사용함.|
<br>

## 이벤트
* jqGrid에서 이벤트를 부여하는 방법은 옵션을 주는 것과 같다. 해당하는 이벤트가 발생할 때를 고려해서 함수를 지정해주면 된다.<br>
  (이벤트 이름 뒤에 오는것은 파라미터이다.)
<br>

|이벤트|역할|
|----|-----|
|afterInsertRow(rowId,rowData,rowElement)|각 줄이 삽입도니 후 일어나는 이벤트이다. 그리드 데이터가 5개 있어서 5줄이 삽입된다면 이벤트도 결국 5번 일어난다.|
|beforeRequest(없음)|서버로 데이터를 요청하기 전에 이루어지는 이벤트이다.|
|gridComplete(없음)|그리드가 모든 작업이 이루어진 후에 발생하는 이벤트이다.|
|loadComplete(data)|서버에 요청을 보낸 직후 호출하는 이벤트이다. data는 Ajax호출 후 받아오는 데이터이다.|
|loadError(xhr,status,error)|서버에 보낸 요청이 실패했을 때 발생하는 이벤트이다.|
|onCellSelect(rowId,indexColumn,cellContent,eventObject)|그리드 셀을 선택하였을 때 발생하는 이벤트이다. 선택한 컬럼의 정보와 셀의 정보도 반환해 줄 수 있다.|
|onSelectRow(rowId,status,eventObject)|그리드의 행을 선택하였을 때 발생하는 이벤트이다. 옵션 중 multiselect로 인해서 체크박스가 활성화 되었을 때, 체크박스의 상태도 반환해 줄 수 있다.|
|onSortCol(index,indexColumn,sortOrder)|정렬하기 전에 (컬럼 헤더를 클릭 후) 발생하는 이벤트|

## 메소드

```jQuery("#grid_id").jqGridMethod( parameter1, ... parameterN );```<br>
```ex)jQuery("#grid_id).jqGrid("setGridParam",{...}).jqGrid("hideCol","somecol").trigger("reloadGrid")```
* grid_id는 그리드가 설정된 ID이다.
* jqGrid는 그리드의 인스턴스이다.
* jqGridMethod는 그리드에서 제공하는 메소드이다.
* 메소드에 따라 parameter가 존재할 수 있다.<br>

### __addRowData(rowId,data,position,srcRowId)__ 그리드에서 행을 추가해주는 메소드이다.

|파라미터 이름|역할|
|---|-----|
|rowId|추가되는 행의 ID를 설정해준다.|
|data|추가될 데이터이다. 기존에 존재하는 데이터의 길이가 같아야 한다.|
|position|데이터가 추가될 위치를 정해준다. 'first','last','before','after' 4가지의 속성이 있다.|
|srcRowId|position의 값이 'before','after'일때 설정해 준다. ID값이 들어온다.|

``` var addData = { ```<br>
&nbsp;&nbsp;```"id" : "006",```<br>
&nbsp;&nbsp;```"name":"영진킴",```<br>
&nbsp;&nbsp;```"age":"26",```<br>
&nbsp;&nbsp;```"sex":"male",```<br>
&nbsp;&nbsp;```"position":"사원"```<br>
```}```<br>
✔ befor 3.6v <br>
```$Grid.addRowData('006',addData,'after','002');```<br>
✔ after 3.6v <br>
```$Grid.jqGrid('addRowData','006',addData,'002');``` <br>

### __getGridParam(name)__ <br>
&nbsp; name에 해당하는 값을 반환해주는 메소드이다. name에 종류로는 그리드 options에 해당하는 값이 올 수 있다.<br> &nbsp;대표적으로 selrow, selarrrow가 자주 사용된다.<br>
* selrow : 선택한 행의 ID를 가지고 옵니다. 여러 행이 선택되었다면 제일 마지막에 선택된 행의 ID를 가지고 온다.
* selarrrow : 여러 행을 선택하였을 때 각각의 ID를 가지고 온다.

✔ before 3.6v <br>
```var selRowId = $Grid.getGridParam('selrow');``` <br>
```var selRowIds = $Grid.getGridParam('selarrrow');``` <br>
<br>
✔ after 3.6v <br>
```var selRowId = $Grid.jqGrid('getGridParam','selrow');``` <br>
```var selRowIds = $Grid.jqGrid('getGridParam','selarrrow);```<br>

### __setGridParam()__
* 그리드 options에 해당하는 값을 수정할 수 있다. 대표적으로 postData,url이 자주 사용된다. 또 setGridParam 메소드는 위에서 설명한 trigger메소드와 같이 자주 사용된다.
* 예를 들어 postData에 검색할 값을 설정하고 바로 trigger메소드를 호출하면 검색한 데이터가 그리드에 그려지는 조회 기능을 구현할 수 있다.

``` var searchData = '검색조건';```<br>
✔getGridParam을 이용해서 postData를 가져온다.<br>
``` var postData = $Grid.jqGrid('getGridParam','postData');```<br><br>
✔postData에 검색할 data 세팅<br>
```postData.search = searchData;```<br><br>
✔setGridParam을 이용해서 postData에 새로 설정해준 postData설정 후 그리드를 다시 불러온다.<br><br>
✔ before 3.6v<br>
```$Grid.setGridParam({'postData' : postData}).trigger('reloadGrid');```<br>
✔ after 3.6v<br>
```$Grid.jqGrid('setGridParam', {'postData' : postData}).trigger('reloadGrid');```



### __trigger("reloadGrid")__ <br>
&nbsp; 그리드를 다시 불러오는 메소드이다. 이메 소드는 그리드의 속성 중 하나인 loadonce 속성이 false인 상태에서만 동작한다.<br>
```$Grid.trigger('reloadGrid');```

