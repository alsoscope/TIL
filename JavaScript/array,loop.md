#### JavaScript - 배열

배열에 값 추가하기

    var arr = ['A', 'B', 'C', 'D'];
    console.log(arr[1]); //값 가져오기
    console.log(arr[3]);
    arr[2] = 3; //값 변환
    console.log(arr);
    console.log(arr.length); //배열의 개수.
    //배열 Index는 0번 방부터 시작. 개수는 평범하게 1부터 센다.

    //배열 끝에 새로운 값 추가하기
    arr.push('E');
    console.log(arr);

배열을 다루는 여러가지 방법들이 존재한다.

#### JavaScript - 배열과 반복문

배열의 element(원소)만큼 반복문을 돌려 값을 더하기

    //배열의 값 출력
    var number = [1, 400, 12, 34, 5];
    var i=0;
    //while 조건문에서 number<5 같은 방법은 정적이다.
    while(number < number.length){
     console.log(number[i]);
     i=i+1;
    }

    var number = [1, 400, 12, 34, 5];
    var i=0;
    var total = 0;
    while(number < number.length){
     total = total + number[i];
     i=i+1;
    }
    //console.log('total :' + total);
    console.log(`total : ${total}`);
    //위의 두 코드의 결과물은 같다. 표현의 차이.
    //문자열과 변수의 값을 같이 출력할 때, 보통 2번처럼 코딩한다.
