__Coding Test Level 1__

## 핸드폰 번호 가리기

전화번호가 문자열 phone_number로 주어졌을 때, 전화번호 뒤의 4자리를 제외한 나머지 숫자를 " * "

로 바꾼 문자열을 리턴하는 함수


> Java Script
---

	function solution(phone_number) {
			var answer = '';

			//.slice() : 배열의 일부분을 선택하여 새로운 배열을 만든다.
			//뒤의 네 자리를 뺀 앞의 숫자들
			var front=phone_number.slice(0,-4);

			//replace() : 특정 문자를 다른 문자로 치환. 정규표현식을 사용할 수 있다
			var answer=phone_number.replace(front, '*'.repeat(front.length));

			return answer;
	}

---

	function solution(phone_number) {
		
	    //뒷자리를 떼고 앞을 '*'로 바꾼 뒤, 다시 붙임
	    return '*'.repeat(phone_number.length-4) + phone_number.slice(-4);
	}

---
	class Solution {
	  public String solution(String phone_number) {
	      String answer = "";

	      String arr[] =phone_number.split("");

	      for(int i=0; i<arr.length-4; i++){
		  arr[i]="*";
	      }
	      for(int i=0; i<arr.length; i++){
		  answer+=arr[i];
	      }

	      return answer;
	  }
	}

---

	class Solution {
	  public String solution(String phone_number) {
	      String answer = "";

	      //뒤의 4자리만 남기고 전부 *로 처리
	      for(int i=0; i<phone_number.length()-4; i++){
		  answer+="*";
	      }

	      //substring()을 이용해서 뒤의 4개 숫자를 덧붙인다. 뒤 4개 숫자만 정상처리
	      answer+=phone_number.substring(phone_number.length()-4, phone_number.length());

	      return answer;
	  }
	}

---

	class Solution {
	  public String solution(String phone_number) {
	      String answer = "";

	      //삼항연산자 조건식 ? 참 : 거짓
	      for(int i=0; i<phone_number.length(); i++){
		  answer+=phone_number.length()-i <= 4 ? phone_number.charAt(i) : "*";
	      }

	      return answer;
	  }
	}

---

	class Solution {
	  public String solution(String phone_number) {
	      String answer = "";

	      //삼항연산자 조건식 ? 참 : 거짓
	      for(int i=0; i<phone_number.length(); i++){
		  answer+=i < phone_number.length() - 4 ? "*" : phone_number.charAt(i);
	      }

	      return answer;
	  }
	}
