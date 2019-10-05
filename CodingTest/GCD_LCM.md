__CodingTest Level1__

## 최대공약수와 최소공배수

최대공약수와 최소공배수 반환하는 함수 solution.<br>
배열 맨 앞에 최대 공약수, 그 다음 최소공배수를 넣어 반환.

예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12] 반환.

- 두 수는 1이상 1000000이하의 자연수

**입출력 예**

|n|m|return|
|--|--|--|
|3|12|[3,12]|
|2|5|[1,10]|

---


package practice;

import java.util.Arrays;
import java.util.Scanner;

public class GCD_LCM {
	
	public static int[] gcdlcm(int a, int b) {
		int[] answer = new int[2];
	    int big, small;
	    int remain = 1;
	    
	      if(a > b){
	          big = a;
	          small = b;
	      }else{
	          big = b;
	          small = a;
	      }    
	    try {
	    	
		    while(remain > 0){
		    	remain = big % small;
		        big=small;
		        small=remain;
		    }
		      
		    System.out.println();
		    answer[0]=big;
		    answer[1]=a*b/big;
		
	    } catch (ArithmeticException e) {
	    	e.printStackTrace();
	    }
	    
		return answer;
	}
	
	public static void main(String args[]) {
		int n, m;
		Scanner scan = new Scanner(System.in);
		n = scan.nextInt();
		m = scan.nextInt();
		System.out.println("main : "  + Arrays.toString(gcdlcm(n, m)));
		scan.close();
	}
}

---
