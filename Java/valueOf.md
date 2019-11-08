valueOf() 함수

valueOf 함수로 감싸는 객체를 원시 데이터형의 값으로 리턴한다.

string.valueOf() : 문자열에 대한 primitive value(원시 데이터형)을 리턴한다.<br>
x = new String("Hello World");<br>
alert(x.valueOf()); //"Hello World"

정수 n을 내림차순으로 배치하는 함수 solution 에서,

	public long solution(long n){

		//인자 n의 원시 값을 공백 단위로 split하여 string 배열[] nArr에 대입한다.
		String[] nArr = String.valueOf(n).split("");

		Arrays.sort(nArr); //배열 오름차순 정렬

		String nStr = new String(""); //nStr 문자열 변수 생성

		//내림차순 정렬. 배열 nArr 총 길이에서부터 0까지 -1씩 감소해 역순으로 nStr에 저장한다.
		for(int i=nArr.length-1; i>=0; i--) nStr += nArr[i];

		return Long.parseLong(nStr);//정수 n의 제한조건으로 인해 Long타입으로 형변환한다.
	}


ret https://opentutorials.org/course/50/101
