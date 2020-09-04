자바 스크립트 URL 관련 내장 함수

    var queryString = window.location.search;
    //window.location : URL query parameters 가져와서 활용

    var newParam = unescape(queryString);
    //unescape : 16진수 문자열 인코딩을 다시 디코딩해줌 ↔ escape

- encodeURI() : 일반 문자열을 16진수 문자열로(percent-encoding) 인코딩
- decodeURI() : 인코딩된 문자열을 일반 문자열로 디코딩

      var newParam2 = decodeURIComponent(queryString);
      //decodeURIComponent() ↔ encodeURIComponent()
      //&, +, = 기호도 인코딩 해준다. Ajax에서 사용

		var urlParams = new URLSearchParams(newParam);
		//URLSearchParams ↓
    `URLSearchParams 인터페이스는 URL의 쿼리 문자열에 대해 작업할 수 있는 유틸리티 메서드를 정의합니다.`<br>
    IE에서 지원안됨.
		
		window.onload = function(){
			document.writeln(newParam2);
		}
    
    //window.onload : https://zuyo.tistory.com/525
    
ref https://twpower.github.io/113-uri-encode-decode-in-javascript<br>
https://developer.mozilla.org/ko/docs/Web/API/URLSearchParams
