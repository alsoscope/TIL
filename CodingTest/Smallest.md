__CodingTest Level 1__

## 제일 작은 수 제거하기

정수를 저장한 배열, arr에서 가장 작은 수를 제거한 배열을 리턴하는 함수 solution을 완성한다.<br>
단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴한다.<br>
예를들어 arr이 [4,3,2,1]인 경우 [4,3,2]를 리턴. [10]이면 [-1]리턴한다.

**제한 조건**
- arr은 길이 1이상인ㅂ ㅐ열
- 인덱스 i, j에 대해 i 이면 arr[i] ≠ arr[j] 이다.

**입출력 예**

|arr|return|
|---|---|
|[4,3,2,1]|[4,3,2]|
|[10]|[-1]|

---

	class Solution {
		public int[] solution(int[] arr) {
				int[] answer = {};

				//제거할 수 있는 수가 없는 배열이라면 -1 리턴
				//(배열이 비었거나 1개의 데이터만 존재)
				if(arr.length == 1){
						return new int[]{-1};
				}

				//최소값 설정. MAX_VALUE는 메소드를 찾을 수 없다하여
				//배열의 0번지 값을 저장한다.
				//int min = Integer.MAX_VALUE();
				int min = arr[0];
				int index=0;

				//최소값 결정
				for(int i=0; i<arr.length; i++){
						if(arr[i]<min){
								min=arr[i];
								index=i;
						}
				}

				answer=new int[arr.length-1];

				//제일 작은 수(index)를 빼고 나머지 복사함
				for(int i=0, j=0; i<answer.length; i++, j++){
						if(index==i) 
								j++;
						answer[i]=arr[j];
				}

				return answer;
		}
	}

---

	class Solution {
	  public int[] solution(int[] arr) {
	      int[] answer = {};

			int min=arr[0];

			for(int i=0; i<arr.length; i++) {
				if(arr[i]<min) {
					min=arr[i];
				}
			}

			if(arr.length -1 == 0) {
				answer=new int[]{-1};			
			}else {
				answer=new int[arr.length -1];
				int index=0;

				for(int num : arr) {
					if(num != min) {
						answer[index] = num;
						index++;
					}
				}
			}

	      return answer;
	  }
	}

---
