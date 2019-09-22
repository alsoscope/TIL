**CodingTest Level1**

## 정수를 담고 있는 배열 arr의 평균값 return
- arr은 길이 1이상, 100이하의 배열
- arr의 원소는 -10, 000 이상 10,000 이하인 정수

__입출력 예__

|arr|return|
|--|--|
|[1,2,3,4]|2.5|
|[5,5]|5|

---

	class Solution {
		public double solution(int[] arr) {
				double answer = 0;

				int sum=0;
				for(int i=0; i<arr.length; i++){
					sum+=arr[i];
				}

				answer=(double)sum/arr.length;

				return answer;
		}
	}

---
