__Coding Test Level 1__

## 하샤드 수 (Harshad Number)

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 함

ex. 18 자릿수의 합은 1+8=9, 18은 9로 나누어 떨어지므로 18은 하샤드 수이다.

자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 solution 함수를 완성해야함.


|arr|return|
|--|--|
|10|true|
|12|true|
|11|false|
|13|false|

---

	package practice;

	public class harshad {	
		public static void main(String[] args) {
			//public boolean solution(){
						//boolean answer = false;
					int x = 18;
						int tmp = x;
						int sum = 0;

						//숫자로 처리하는 방법. 10의 배수로 만들어 나머지를 취해 얻어낸다.
						while(tmp/10 != 0){
								sum += tmp%10;
								tmp= tmp/10;
						} 
						sum+=tmp;

						if(x%sum == 0){
								System.out.println("true");
						}else{
							System.out.println("false");
						}
						//return answer;
		}
	}

---

	package practice;

	public class harshad2 {	
			public boolean solution(int x){
						boolean answer = false;
					//int x = 18;
						int tmp = x;
						int sum = 0;

						while(tmp/10 != 0){
								sum += tmp%10;
								tmp= tmp/10;
						} 
						sum+=tmp;

						if(x%sum == 0){
						answer = true;
						}else{

						}
						return answer;
		}//solution

		public static void main(String[] args) {
			harshad2 har = new harshad2();
			System.out.println(har.solution(18));
		}//main
	}//harshad2
	
---
	
	package practice;

	import java.util.Scanner;

	public class harshad3 {
		public static void main(String[] args) {
			Scanner scan = new Scanner(System.in);

			int x = scan.nextInt();

			System.out.println(solution(x));

			scan.close();
		}//main

			public static boolean solution(int x){
						int tmp = x; //입력받은 정수로 자릿수의 합을 계산하기 위한 임시 변수.
						int sum = 0; //자릿수의 합.

						while(tmp/10 != 0){
								sum += tmp%10; //x를 10으로 나누어 나머지는 자릿수로 sum에 누적.
								tmp= tmp/10; //다음 자릿수를 위해 나누다.
						} 
						sum+=tmp; //제일 마지막에 남는 몫이 마지막 자릿수이기에 sum에 누적.

						System.out.println("sum 합계  : " + sum);

						//입력값을 자릿수의  합으로 나누었을 때 떨어지면
						if(x%sum == 0){
						return true; //하샤드 수이므로 true.
						}	      
						return false;

		}//solution
	}//harshad2
	
---

	package practice;

	import java.util.Scanner;

	public class harshad4 {

		public static void main(String[] args) {
			System.out.println("하샤드 수를 알아볼 정수 입력");
			Scanner scan = new Scanner(System.in);

			int x=scan.nextInt();
			System.out.println(solution(x));
			scan.close();
		}//main

		public static boolean solution(int x) {
			boolean answer=false;

			//문자열과 char배열로 만들어 각각의 char 데이터를 얻어내 String으로 변환하여 처리하는 방법이 있다.
			String strx = x + "";//공백을 더함
			char[] charx = strx.toCharArray();//char배열로 만드는 toCharAttray() 메소드
			int sum = 0;

			for(int i=0; i<charx.length; i++) {
				sum+=Integer.parseInt(charx[i]+"");//이를 다시 parseInt로 숫자로 만든다.
			}
			System.out.println("sum 누적 합계 : " + sum);

			if(x%sum == 0) {
				answer = true;
			}
			return answer;
		}//main
	}//harshad4
	
---

	package practice;

	public class harshad5 {
		public static void main(String[] args) {
			//문자열로 만들어서 length만큼 각각 자르는 방법

			int x = 18;
			//split(문자열,"") ""공백 : split 메소드로 문자열 하나씩 쪼갠다.
			String[] temp = String.valueOf(x).split("");
			int sum = 0;

			//쪼개진 문자를 int로 타입변환하여 처리
			for (String s:temp) {
				sum+=Integer.parseInt(s);
				System.out.println("sum 누적 합계 : " + sum);
			}

			if(x%sum==0) {
				System.out.println("true");
			} else {
				System.out.println("false");
			}
		}
	}//harshad5

---
