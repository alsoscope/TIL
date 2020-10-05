Delete,Put,Patch Mapping 사용

---

HiddenHttpMethodFilter 추가

    @Bean
    public HiddenHttpMethodFilter filter() {
      HiddenHttpMethodFilter filter = new HiddenHttpMethodFilter();
      return filter;
    }

GET/POST만 지원하는 브라우저에서 RESTful 기능인 PUT, PATCH, DELETE 가능케 해줌.

---

Spring Form Tag 사용을 위한 JSTL 태그 라이브러리 추가

    <%@ taglib prefix="form" uri="http://www.springframework.org/tags/form" %>

    <form:form action="/board_Delete/${board.bno }" method="DELETE">
      <input type="submit" value="삭제">	
    </form:form>

위와 같이 전송하면

내부적으로 이런 형식으로 전달됨

    <input type="hidden" name="_method" value="DELETE">

하지만 나는 그냥 일반적인 HTML form 에 위의 input hidden 태그를 추가했다.<br>
action="/board_Delete/${board.bno }" form 태그에 추가해서 컨트롤러 매핑.

ref https://www.hanumoka.net/2018/09/02/spring-20180902-Spring4-Rest-HiddenMethod/<br>
https://bbiyakbbiyak.tistory.com/1


---

Ajax 로 처리할 수 있다.

컨트롤러에서 json으로 응답
