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

JSP에서 <c:url value="URL 주소"/> 이렇게만 실행시키면 화면에 URL 주소가 찍힘

- c:redirect<br>
페이지 이동. response.sendRedirect() 와 같은 기능.


        <c:redirect url="[필수]이동할 URL" />
        
><jsp:forward> 액션태그. 서버사이드에서 구현된 요청 형태만 포워딩.<br>
같은 서블릿 컨텍스트 내의 다른 페이지로만 이동.

- c:import<br>
지정된 URL을 태그가 사용된 JSP 페이지에 출력, 첨부<br>
URL 속성에는 HTTP 뿐만 아니라 FTP 외부 리소스를 JSP 페이지에 삽입. (내부, 외부 자원)

       <c:import url=""/>
    
css, gif 같은 자원들이 404 Not Found 될 수 있다.

>HTML의 include 역할

동적인 방식 <jsp:include page=""><br>
정적인 방식 <%@ include file="" %> 지시자<br>
같은 웹 어플리케이션/Servlet Context 안에 있는 페이지만 불러들인다.

ref https://anyframe.tistory.com/375<br>
https://hackersstudy.tistory.com/42<br>
https://itjava.tistory.com/71<br>
http://theeye.pe.kr/archives/1563
