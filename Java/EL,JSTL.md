JSP

#### JSTL fn 함수

    <%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions"%>

  - startsWith(str1, str2)<br>
    str1이 str2로 시작할 경우 true, 그렇지 않을 경우 false 리턴

#### JSTL Core

    <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>

- c:set<br>
JSP의 setAttribute() 와 같은 역할

var : 변수명<br>
value : 값. EL ${} 사용<br>

    <c:set value="0" var="sum"/><br>
    <c:set value="${sum}" var="amount"/>

- c:url<br>
URL을 생성해준다

    <c:url var="[선택]변수명" value="[필수]URL주소" />

- c:redirect<br>
페이지 이동

    <c:redirect url="[필수]이동할 URL" />


ref https://anyframe.tistory.com/375<br>
https://hackersstudy.tistory.com/42<br>
https://itjava.tistory.com/71
