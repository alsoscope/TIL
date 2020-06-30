orwarding 방식

### RequestDispatcher
클라이언트로부터 들어오는 요청에 따라 원하는 Servlet, JSP로 제어를(요청 객체 request) 넘겨, 그 결과를 응답한다.

- forward() 메서드<br>
forward(request, response);<br>
브라우저로부터 a.jsp가 요청받았을 때 a에서 forward()를 실행하여 자원을 b.jsp로 제어를 넘길 수 있다.<br>
브라우저가 요청한 건 a이지만 결과는 b로 받는다.<br>
하나의 HTTP 요청request 범위 안에서 동작이 이루어진다. URL 주소가 변경되지 않음.<br>
a 요청, b 처리, 그 결과 내용을 a에서 보여줄 수도 있다.<br>
request scope(request, response)에 담긴 값이 유지된다.

- 컨트롤러 사용

    RequestDispatcher rd = request.getRequestDispatcher("/a.jsp");
    request.setAttribute("abc", a);
    rd.forward(request, response);

JSP에서 EL ${} 이나 request.getAttribute 로 값을 받아볼 수 있다.

- JSP 사용

    <% RequesDispatcher rd = application.getRequestDispatcher("/a");
       rd.forward(request, response)
    %>

include() 메서드

#### Redirect HttpServletResponse
새로운 요청이 만들어짐. request 유지되지 않고 새로운 Request와 Response 요청 객체가 생성됨.<br>
set해서 get을 위임받은 컴포넌트에서는 사용할 수 없다.<br>
바뀐 URL이 표시된다.

response.sendRedirect("");
