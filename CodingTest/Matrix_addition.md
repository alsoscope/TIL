**Coding Test Level1**

## 행렬의 덧셈 (Matrix Addition)

행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은  행, 같은 열의 값을 서로 더한 결과

2개의 행렬 arr1, arr2를 입력받아 행렬 덧셈의 결과를 받환하는 함수 soulution 완성하기

- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않는다

__입출력 예__

|arr1|arr2|return|
|:--|:--|:--|
|[[1,2],[2,3]]|[[3,4],[5,6]]|[[4,6]],[7,9]]|
|[[1],[2]]|[[3],[4]]|[[4],[6]]|

---

	class Solution {
		public int[][] solution(int[][] arr1, int[][] arr2) {
				int[][] answer = new int[arr1.length][arr1[0].length];

				for(int i=0; i<arr1.length; i++){
						for(int j=0; j<arr1[0].length; j++){
								answer[i][j] = arr1[i][j] + arr2[i][j];
						};
				};

				return answer;
		}
	}

---

***

	class Solution {
		public int[][] solution(int[][] arr1, int[][] arr2) {
				//int[][] answer = {};

				int row = Math.max(arr1.length, arr2.length);
				int col = Math.max(arr1[0].length, arr2[0].length);
				int[][] answer = new int [row][col];
				//int[][] answer = new int={{0,0},{0,0}};

				for (int i=0; i<row; i++){
				 for(int j=0; j<col; j++){
						 answer[i][j]=arr1[i][j]+arr2[i][j];
				 };
				};

				return answer;
		}
	}

***
