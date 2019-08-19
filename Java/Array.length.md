__2차원 배열__

- 배연 선언, 초기화

int[][] array;

int array[][];

int[] array[];

int[][] array = new array[4][3]; //array[0][0]부터 array[4][3]까지 12개의 int값을 저장할 수 있는 공간이 생성됨.

	int array[][] = new array[][] {{1,2,3},{4,5,6}};

	int array[][] = {{1,2,3},{4,5,6}}; //new int[][] 생략

	int array[][] = {
		{1,2,3},
		{4,5,6}
	}; //행별로 줄바꿈

- 길이
int[][] array = new int[][];
에서

array.toString을 하면 첨자변수의 저장 주소가 출력됨

array.length    → 행 길이

array[0].length → 열 길이

	for(int i=0; i<array.length; i++){      → 행 길이만큼
		for(int j=0; j<array[i].length; j++){ → 열 길이만큼

		}
	}
