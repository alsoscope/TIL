**Coding Test Level1**

## x만큼 간격이 있는 n개의 숫자

정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트 반환
- x는 -10000000 이상, 10000000 이하인 정수
- n은 1000 이하인 자연수

__입출력 예__

| x | n | answer |
|:---:|:---:|---|
| 2 | 5 | [2,4,6,8,10] |
| 4 | 3 | [4,8,12] |
| -4 | 2 | [-4,-8] |

int 최대값 약 -21억~21억 저장
자연수 * 조건로 answer[i]에는 int 가 저장되지만 제한 조건 때문에 초과됨.
그렇기에 Long.valueOf 으로 형변환한다.

---

	class Solution {
	  public long[] solution(int x, int n) {
	      long[] answer = {};

	      answer=new long[n];

	      for(int i=0; i<n; i++){
		answer[i]=(Long.valueOf(x)*(i+1));    
	      }

	      return answer;
	  }
	}
	
---
