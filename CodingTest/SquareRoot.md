__CodingTest Level 1__

## 정수 제곱근 판별하기

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 함.<br>
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1 리턴하는 함수 완성하기.

- n은 1이상, 50,000,000,000,000이하의 양의 정수

**입출력 예**

|n|return|
|--|--|
|121|144|
|3|-1|

- 121은 양의 정수 11의 제곱이므로 (11+1)를 제곱한 144를 리턴한다
- 3은 양의 정수의 제곱이 아니므로 -1을 리턴한다

---

	class Solution {
		public long solution(long n) {
				long answer = 0;

				int i=(int)Math.sqrt(n);
				double d=Math.sqrt(n);

				if(i==d){
						answer = (long)Math.pow(d+1, 2);     
						return answer;
				}else{
						return -1;
				}
		}
	}

---

	class Solution {
	  public long solution(long n) {
	      long answer = 0;

	      int i=(int)Math.sqrt(n);
	      double d=Math.sqrt(n);

	      return i == d ? (long)Math.pow(i+ 1 , 2) : -1;
	  }
	}

