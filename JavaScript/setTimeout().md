### 자바스크립트 타이머 함수

### setTimeout()
일정 시간을 지정해 특정 코드, 함수를 실행한다.

      setTimeout(function(){
        //code here,
      }, delay );

1. 호출될 콜백함수
2. 지연시간(delay time)

콜백함수로 지연시간 뒤에 실행될 코드를 설정한다.
지연시간은 밀리세컨드 단위. 1000은 1초 10000은 10초를 의미.

- 3초의 지연시간 설정 예제

        setTimeout(function(){
          console.log("works");
        }, 3000);
        //3초 뒤 함수가 실행됨

+ setTimeout()의 활용방법.
  웹사이트 개발시 가장 많이 사용되는 경우에는
  - 접속 후 몇 초 후에 팝업 또는 배너창 띄우기
  - 방문자의 스크롤이 브라우저 일정 위치에 올 경우 몇 초 뒤에 애니메이션 실행
  - 검색창 또는 일부 섹션 몇 초 뒤에 사라질 경우
  - 방문자 접속 후 20-30초가 지난 뒤 메일 구독을 신청하는 팝업창을 띄울 경우 등등..

- 예제

        setTimeout(function(){
          alert("setTimeout");
        }, 3000);
        //3초 뒤 경고창으로 해당 문구를 출력. 3초 뒤 콜백함수 실행

만약 계속해서 3초마다 출력하려면,
일정시간마다 반복해서 코드를 실행하는 함수인 **setInterval()** 을 사용할 수 있다.

__clearTimeout()__

타이머 함수를 중지, 삭제하는 함수<br>
setTimeout() 을 사용하면 숫자 타입의 값을 반환함. 실행을 중지할 경우,<br>
즉 남아있는 시간을 해제할 경우 clearTimeout()을 설정해야한다

setTimeout() 함수를 myTimer에 담은 후 이를 clearTimeout()으로 해제, 삭제하는 예제

      var myTime=setTimeout(function(){
        //Timer codes
      }, 3000);

      clearTimeout(myTimer);

---

setTimeout() 함수와 생각해 볼 부분

- setTimeout()을 사용한 반복 코드 구현과 setInterval()<br>
setTimeout()을 사용하여 계속 반복하는 코드를 만들 수 있다. setInterval()과 매우 비슷하다.<br>
다만 시간단위가 아닌 이전의 setTimeout()이 끝나야 동작하게 됨.
시간이 아닌 큐에 의하여 동작하게 된다.

> Queue : 컴퓨터의 기본적인 자료 구조의 한 가지.<br>
먼저 집어넣은 데이터가 먼저 나오는 FIFO (First In First Out)구조로 저장하는 형식

- 메모리 누수(Memort Leak)의 발생<br>
페이지가 전환되지 않는 경우, 싱글 페이지(SPA)인 경우 사용되지 않는 setTimeout() 코드가 메모리에<br>
계속 남아 있을 수 있으며, 가비지 컬렉션(GB)에 의해 회수되지 않는 경우는 성능저하에 원인이 되므로,<br>
setTimeout() 이벤트는 이벤트를 제거하는 코드 역시 필요하다. clearTimeout()은 설정된 setTimeout()을 제거하는 함수

ref https://webisfree.com/2014-04-08/[javascript]-%EC%8B%9C%EA%B0%84-%EC%A7%80%EC%97%B0-%ED%95%A8%EC%88%98-%EC%9D%BC%EC%A0%95-%EC%8B%9C%EA%B0%84-%EB%92%A4-%EC%8B%A4%ED%96%89%EC%8B%9C%ED%82%A4%EA%B8%B0-settimeout()-%7B%7D
