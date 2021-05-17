# JAVA

## 객체지향 프로그래밍이란?
### 1.객체지향 프로그래밍이란?
* 객체지향 프로그래밍(Object-Oriented Programming)이란 프로그램을 설계하는 개념이자 방법론이다.<br>
  줄여서 OOP라고 부르며, 단어 뜻 그대로 프로그램(실제세계)를 객체(사물)라는 기본 단위로 나누고 이 객체들간의 상호작용을 기본개념으로 한다.
* 객체지향 프로그래밍(OOP)은 프로그램을 유연하고 변경하기 쉽게 만들기 때문에 재사용성이 용이하여 대규모 프로젝트에서 많이 사용되는 방법론이다. 프로그램 개발과 유지보수가 용이하다는 점이
  가장 큰 장점으로 꼽힌다.

### 2.객체지향 vs 절차지향
|비교|절차지향 언어|객체지향 언어|
|--|----|----|
|장점|-처리속도가 빠르다<br>-초기프로그래밍언어로 컴퓨터의 처리구조와 비슷해<br>실행속도가 빠르다.|-코드 재사용성이 용이하다.<br>-개발(코딩)이 간단하다.<br>-유지보수가 쉽다.<br>-대규모 프로젝트에 적합하다.|
|단점|-유지보수가 어렵다<br>-대규모 프로젝트에 부적합하다.<br>-프로그램 분석이 어렵다.|-처리속도가 느리다.<br>-객체에 따른 용량증가<br>-설계단계에 시간이 많이 소요된다.|

## 객체지향의 특징 4가지(추상화,캡슐화,상속,다형성)

### 1.추상화(Abstraction)
* 객체 지향에서 추상화란 객체에서 공통된 속성과 행위를 추출하는 것을 의미한다.<br>
  예를 들어, 게임 프로그램을 개발하며 캐릭터가 소지하는 다양한 무기들이 있다. 칼,삽,곡괭이,총,활 등 여러가지 무기들이 존재하는데 이들의 기능적인 내용은 다르지만 공통적인 속성과
  행위를 개념으로 무기라는 클래스를 정의할 수 있다. <br>
  이렇듯 추상화는 다른 객체들과 구분되는 핵심적인 부분에 집중하여, 복잡도를 관리할 수 있게 해준다.
  
### 2.캡슐화(Encapsulation)
* 캡슐화는 연관있는 변수와 메소드를 묶어주는 작업을 말한다.<br>
  접근 제어 지지자(public,private,protected)를 통해 외부로부터 접근을 제한하여 객체내에서만 접근이 가능하도록 해주며, 이를 정보 은닉이라 한다.<br>
  외부의 클래스 혹은 모듈에 의존적인 프로그램의 경우 변경이나 오류에 취약해지는데, 정보은닉을 통해 이러한 결합도를 낮추며 응집도를 높여준다.

## Collection(List,Set,Map)의 종류와 이해

### 1.JAVA Collection Framework
* JAVA에서 기본적인 자료구조를 제공하기 위한 환경
![다운로드](https://user-images.githubusercontent.com/72905696/118445618-a255b480-b729-11eb-8904-742eb74f185b.png)<br>
JAVA Collection Framework의 상속 기본 구조
***
### 2.각 인터페이스의 특징
|인터페이스|구현클래스|특징|
|---|---|-----|
|List|LinkedList<br>Stack<br>Vector<br>ArrayList|순서가 있는 데이터의 집합, 데이터의 중복을 허용함|
|Set|HashSet<br>TreeSet|순서를 유지하지 않는 데이터의 집합, 데이터의 중복을 허용하지 않음|
|Map|HashMap<br>TreeMap<br>HashTable<br>Properties|키(key)와 값(value)의 쌍으로 이루어진 데이터의 집합<br>순서는 유지되지 않고, 키는 중복을 허용하지 않으며 값의 중복을 허용함|

### 3.Collection 인터페이스들의 특징
* Collection 인터페이스를 상속받아 List와 Set인터페이스가 된다.

### List 인터페이스의 특징
* 순서가 있는 Collection(여기서 순서는 삽입된 순서를 의미한다.)
* Data를 중복해서 포함 할 수 없다.

__1. ArrayList의 특징__
* 동기화를 보장해주지 않는다.
* 배열에 동적 메모리 증가 기능을 구현한 클래스이다.
* 동기화 지원 방법 : List list = Collection.synchronizeList(new ArrayList(...));
* add() method : Data를 삽입할 때 사용
* get() method : Data를 추출할 때 사용
* toArray() method : ArrayList로 부터 배열을 얻어낼 때 사용
* contains() method : Data의 존재 유무를 알기 위해 사용
* size() method : ArrayList의 요소 개수를 얻어낼 때 사용

### Set 인터페이스의 특징
* 집합적인 개념의 Collection
* 순서의 의미가 없다.
* Data를 중복해서 포함 할 수 없다.

__1. HashSet의 특징__
* add() method : Data를 삽입할 때 사용
* next() method : Data를 추출할 때 사용(HashSet의 Data추출은 Iterator를 이용하면 됨)
* remove() method : Data를 삭제할 때 사용
* contains() method : Data의 포함여부를 알기 위해 사용
* size() method : HashSet의 요소 개수를 얻어낼 때 사용

### Map 인터페이스들의 특징
* List와 Set이 순서나 집합적인 개념의 인터페이스라면 Map은 검색의 개념이 가미된 인터페이스이다.
* Map인터페이스는 데이터를 삽입할 때 Key와 Value의 형태로 삽입되며, Key를 이용해서 Value를 얻을 수 있다.

__1. Hashtable, HashMap의 공통점__
* 내부적으로는 모두 Hash 기법을 이용한다.
* Map 인터페이스를 구현하고 있다.
* Key와 Value를 이용해서 Data를 관리한다.

__2. Hashtable과 HashMap의 차이점__
* Hashtable은 동기화가 보장된다.
* HashMap은 동기화가 보장되지 않는다.
* HashMap의 동기화 지원 방법 : Map m = Collections.synchronizedMap(New HashMap(...));

__3. Hashtable, HashMap과 HashSet과의 관계__
* Hashtable과 HashMap은 둘 다 Map 인터페이스를 구현하고 있다.
* HashSet은 내부적으로 Hash기법을 사용하지만 Set인터페이스를 구현하고 있다.

__4. HashMap__
* 객체 생성 : ```Map<String,Integer> map = new HashMap<String,Integer>();```
* put() method : Data 삽입할 때 사용
* get() method : Data를 추출할 때 사용, argument값은 Key를 사용

__5. HashTable__
* 객체 생성 : ```Hashtable<String,Object> h = new Hashtable<String,Object>();```
* put() method : Data를 삽입할 때 사용
* get() method : Data를 추출할 때 사용, argument값은 Key를 사용

### Sorted 인터페이스들의 특징
* Set과 Map 인터페이스를 상속받아 정렬 기능이 추가된 SortedSet과 SortedMap 인터페이스가 된다. 그리고 이들은 각각 TreeSet클래스와 TreeMap클래스로 구성된다.
  TreeSet과 TreeMap은 Set과 Map의 기능을 가지고 있으면서 정렬 기능이 가미되었다는 것이 특징이다.

__1. Sorted를 지원하지 않는 클래스__
* HashSet, HashMap

__2. Sorted를 지원하는 클래스__
* TreeSet, TreeMap

__3.TreeMap__
* Key와 Value로 Data를 관리
* Key를 기준으로 오름차순으로 정렬된다.
* Map 인터페이스를 상속한 SortedMap 인터페이스를 구현한 클래스

__4.TreeSet__
* Set인터페이스를 상속한 SortedSet 인터페이스를 구현한 클래스
* 데이터들이 자동으로 오름차순으로 정렬된다.

__5.Comparator__
* TreeSet과 TreeMap은 사용자가 직접 정렬의 방식을 지정할 수 있다.
* TreeSet과 TreeMap은 정렬을 위한 Comparator 인터페이스를 구현하면 된다.
* TreeSet에 Data를 집어넣으면 기본적으로 오름차순(Ascending) 정렬이 되지만 그것도 문자열이나 기본 데이터 타입과 같은 단순한 것에만 해당된다.
  이에 사용자가 직접 비교법을 넣어주기 위해 사용하는 것이 Comparator 인터페이스이다.
