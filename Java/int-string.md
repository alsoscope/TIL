숫자 타입(Integer, Long...)을 String으로 변환.

매개변수 long n에 대하여

String str=new String(n+"");

String str=String.valueOf(n);

String str=Long.toString(n);

String str= "" + n;


- 프로그래머스 자릿수 더하기 예제

      int answer=0;

      //int 값을 string 문자열로 변환
      String temp=String.valueOf(n);

      for(int i=0; i<temp.length(); i++){
        //자릿수를 한 자리씩 자른 후 int로 변환
        answer=answer+Integer.parseInt(temp.substring(i, i+1));
      }

substring(int beginIndex, int endIndex) : 특정 기준으로 문자열을 자름<br>
첫 번째 인자는 시작점, 두 번째 인자는 끝내는 점
