**문자열 관련 내장함수**

## substring() 문자열 자르기

문자열을 원하는 위치에서 자를 수 있다.<br>
문자열 Index는 0번 부터 시작한다.

- int 인자가 1개일 때<br>
.substring (int index) : 해당위치를 포함하여 이후의 모든 문자열 리턴한다.

- 인자가 2개일 때<br>
.substring(int startIndex, int endIndex)

가져올 문자열의 시작부터~ 끝부분의 전까지 지정한다.

	String str='000012583972445';
	str.substring(4,12);

이라면 4번째 인덱스의 1과 endIndex의 12번째 전의 값인 2가 리턴됨.  

## split() 문자열 구분

.split(" ")<br>
공백으로 쪼갬

.split("")<br>
문자열을 구분해서 사용하고 싶을 때 특정 문자를 기준으로 나누어 배열에 저장해 이용한다.

일부러 데이터베이스 데이터 문장 끝에 +,#같은 특수기호를 넣어 나중에 값을 꺼낼 때 그 기호로 split하여 사용할 수 있다.

> 인자가 1개일 때
split(String index) : 문자열을 구분

	String number="010-2333-4343";
	String[] num=str.split("-"); 
"-"로 split하여 배열에 저장, 배열 인덱스 각 저장된 값을 꺼낼 수 있다.

> 인자가 2개일 때
split(String firstIndex, int lastIndex) : 첫 번째 인자는 문자열을 구분, 두 번째 인자는 배열의 크기를 결정한다.

	String number="010-2333-4343";
	String[] num=str.split("-", 2);
	
"-"를 인자 값으로 split하면서 배열의 크기를 2로 한정한다.<br>
두 개의 배열에는 각각 010과 나머지 뒷 자리가 저장됨.

데이터 39-88-7-478-45785 가 저장되어있고,<br>
string[] num2=str.split("-", 4); 라면,<br>
0부터 3번까지의 배열에 각각 39,88,7,478-45785가 저장된다.

메타문자로 들어가는 특수문자를 사용할 때는 이스케이프 처리한다. 역 슬래쉬 두 번.

## charAt() 인덱스 위치에 해당되는 문자 추출

	String words="안녕하세요";
	char word=words.charAt(3); //"세"
	system.out.println(word);

## 자바 문자열 비교 메소드

- __.equals()__<br>
equals() 메소드는 대소문자를 구분하여 비교

- **.equalsIgnoreCase()**<br>
equalsIgnoreCase() 메소드는 대소문자를 구분하지 않고 비교

## indexOf()
문자열 중 입력받은 문자가 있으면 해당 문자의 위치(index) 값을 리턴하고,<br>
문자가 없으면 -1 리턴

	String str = "Hello world";
	System.out.println(str.indexOf("e"));
	//index 값인 1리턴
	//"wo" 를 찾으려 할 경우 6리턴 

## replaceAll()
특정 문자열을 원하는 문자열로 치환

replaceAll(String regex, String replacement)<br>
첫 번째 인자는 변환하고자 하는 대상이 되는 문자열, 두 번째는 변환할 문자값

	String str = "Hello world";
	System.out.println(replaceAll("ll", "!!"));//He!!o world

	String str2 = "Hello world";
	System.out.println(replaceAll("o w", "오 더블유"));//Hell오 더블유orld

ref https://jamesdreaming.tistory.com/84 https://coding-factory.tistory.com/126
