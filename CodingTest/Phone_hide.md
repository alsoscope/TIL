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
