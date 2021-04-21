Ajax - JSON 통신 중 CORS 크로스 사이트 스크립트 어쩌구 발생 때문에<p>
데이터를 제대로 못받음
<br><br>
URL 호출하는 자바 소스코드에 헤더 추가

<pre><code>
response.setHeader("Access-Control-Allow-Methods", "GET");
response.setHeader("Access-Control-Max-Age", "3600");
response.setHeader("Access-Control-Allow-Headers", "x-requested-with");
response.setHeader("Access-Control-Allow-Origin", "*");
</code></pre>

ajax 데이터타입 jsonp 또는 <p>
응답받는 jsp 파일에 헤더를 추가해도 된다고 한다.

ajax beforeSend? 추가하니까 또 CORS <br>
스프링부트 어노테이션 추가로 해결<br>
@CrossOrigin(origins="*", maxAge=3600)

참조
https://developer.mozilla.org/ko/docs/Web/HTTP/Headers/Access-Control-Allow-Origin <br>
https://roynus.tistory.com/52 <br>
https://adrenal.tistory.com/16

<br>
ajax 통신 참고<p>
https://sugerent.tistory.com/66
 
