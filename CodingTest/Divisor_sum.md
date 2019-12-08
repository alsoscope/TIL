## 약수의 합

- 정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수 solution 완성

> 제한사항
  >> n은 0이상 3000이하의 정수

* 입출력 예

|n|return|
|--|--|
|12|28|
|5|6|

  + 입출력 예 1 ) 12의 약수는 1,2,3,6,12. 이를 모두 더하면 28이다.
  + 입출력 예 2 ) 5의 약수는 1,5. 모두 더하면 6이다.

---

      class Solution {
        public int solution(int n) {
            int answer = 0;

            for(int i=1; i<=n; i++){
                if(n%i == 0){
                 answer+=i;   
                }
            }     
            return answer;
          }
      }

---
