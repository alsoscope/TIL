### DB에서 가져온 Timestamp를 자바에서 가공하여 JSP로 출력하기

자바에서 Timestamp형 Date를 String 변수에 담으면 된다.

.class

    String insertDate=dto.getInsertDate();

.jsp

    <%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

    <!-- parseDate로 String → Date 형 변환 -->
    <fmt:parseDate value="${list.insertDate }" var="insertDate" pattern='yyyy-MM-dd'></fmt:parseDate>


    <!-- 숫자로 변환된 두 데이터를 연산 후 formatNumber 등으로 원하는 포맷과 단위로 화면에 출력 -->
    <td><fmt:formatDate value="${insertDate }" pattern='yyyy-MM-dd'/>일</td>
