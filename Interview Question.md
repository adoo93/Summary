# 간단한 기술 면접 예상 질문

### Inner Join과 OuterJoin이란 무엇이며 어떻게 사용되는가?
* Inner Join이란 조인되는 키 값을 기준으로 둘 이상의 테이블에 존재하는 데이터를 조회하는 것이며 Simple Join이라고도 한다.
  집합으로 표현하자면 교집합이라고 할 수 있다. NULL 값은 포함되지 않는다.
  
* ex) SELECT * FROM TABLE1 t1<br>
       　 　INNER JOIN <br>
       　 &nbsp;TABLE2 t2 <br>
       　 　ON <br>
     　 (t1.컬럼1 = t2.컬럼2);<br>
---> NULL을 제외한 TABLE1과 TABLE2의 교집합을 보여준다.

* Outer Join이란 Inner Join과는 다르게 두 테이블에서 지정된 쪽의 (LEFT or RIGHT) 모든 결과를 보여준 후 반대쪽에 매칭되는 값을 보여주고, NULL값까지 포함하는 join이다.
  Outer Join의 종류로는 left,right,fullover,outer join 이 있다.
  
* ex) SELECT * FROM TABLE1 t1<br> 
      　 　LEFT JOIN<br> 
       　&nbsp;&nbsp;TABLE2 t2<br> 
        　 　ON <br>
        　&nbsp;(t1.컬럼1 = t2.컬럼2);<br>
      　 SELECT * FROM TABLE1 t1<br> 
         　 　RIGHT JOIN<br> 
       　&nbsp;TABLE2 t2<br> 
          　 　ON<br> 
        　&nbsp;(t1.컬럼1 = t2.컬럼2);<br>
---> LEFT는 왼쪽테이블 t1을 기준으로 세우는 join / Right는 오른쪽 테이블 t2를 기준으로 세우는 join       
  
  ex)  SELECT * FROM TABLE1 T1<br>
         　 　FULL OUTER JOIN<br>
       　 &nbsp;TABLE2 t2<br>
         　 　ON<br>
       　&nbsp;(t1.컬럼1 = t2.컬럼2);<br>
---> LEFT와 RIGHT를 합친 것과 같다.
      
