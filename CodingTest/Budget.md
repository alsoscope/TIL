**CodingTest Level 1**

## 예산
부서별 물품 지원 예산 구하기.
모든 부서의 물품 구매 X, 최대한 많은 부서의 물품을 구매하도록 한다.
그 부서의 신청 금액 모두 지원.

신청한 금액이 들어있는 배열 d 와 예산 budget이 매개변수로 주어질 때,
최대 몇 개의 부서에 물품을 지원할 수 있는지 return 하도록 하는 solution 함수를 완성하도록 한다.

- d는 부서별로 신청한 금액이 들어있는 배열, 길이(전체 부서의 개수)는 1이상 100이하
- d의 각 원소는 부서별로 신청한 금액을 나타냄. 부서별 신청 금액은 1이상 100,000이하의 자연수
- budget은 예산을 나타냄. 1이상 10,000,000이하의 자연수


__입출력 예__

| d | budget | result |
|:---:|:---:|:---:|
| [1,3,2,5,4] | 9 | 3 |
| [2,2,3,3] | 10 | 4 |

입출력 예 1(각 부서에서 [1,3,2,5,4]만큼의 금액을 신청, 예산 9원과 비교하여 해당하는 만큼 지원한다)
입출력 예 2([2,2,3,3]의 부서의 모든 물품을 구매해주면 10원이 되기에 최대 4개 부서의 물품을 구매해 줄 수 있다)


Array.sort()를 이용한 오름차순 정렬
예산을 초과하면 종료(budget이 0이 되거나, 나머지 예산과 남은 신청 금액이 맞지 않을 때)

---
	import java.util.Arrays;
	
	class Solution {
		public int solution(int[] d, int budget){
			//answer는 예산을 지원해준 부서의 개수를 나타냄
			int answer=0;
			
			//최대한 많은 부서에(d 배열) 예산을 지원하는(return answer) solution 함수
      
		       //많은 부서를 지원하기 위해선 적은 신청 금액의 부서를 budget에서 먼저 빼준다
		       //적은 금액부터 정리하려면 먼저 배열을 오름차순으로 정리한다
		       //Arrays.sort()는 배열을 오름차순 정렬하는 함수
			Arrays.sort(d);
			
			//예산이 0이 되거나, 남은 예산보다 나머지 신청 금액이 클 경우 종료하도록 한다
			for(int i=0; i<d.length; i++){
			  if(budget==0 || budget<d[i]){
			      break;
			  }
			  budget-=d[i];
			  answer++;
		      }
			
		return answer;
		}
	}
	
	error: cannot find symbol
     	 Arrays.sort(d);
	 //import java.util.Arrays;
	 
---

	import java.util.Arrays;

	class Solution {
	  public int solution(int[] d, int budget) {
	      int answer=0;
	      int result=0;

	      Arrays.sort(d);

	      //배열 하나씩 더해가며 값을 비교, 다 더했는데도 budget보다 크지 않다,
	      //같거나 작다면 최대값은 배열의 길이와 같다
	      for(int i=0; i<d.length; i++){
		  result+=d[i]; //작은 값부터 더해가며 비교
		  if(result > budget) {
		      answer=i;
		      break;
		  }
	      }
	      //budget보다 클 때 종료하거나, 다 더했는데 작거나 같은 경우 예외적으로 처리한다
	      if(result <= budget){
		  answer=d.length;
	      }
	      return answer;
	  }
	}

***

	import java.util.Arrays;

	class Solution {
	  public int solution(int[] d, int budget) {
	      int answer=0;

	      Arrays.sort(d);

	      for(int i=0; i<d.length; i++){
		  budget -= d[i];
		  if(budget < 0) break;
		  answer ++;
	      }
	
		//for문 완전히 빠져나오면 이미 최대값을 지났다는 뜻이므로 그 값이 결과값이 되어 return됨
	      return answer;
	    }
	}
