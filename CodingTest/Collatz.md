**Coding Test Level1**

## 콜라츠 추측

> 1937년 Collatz란 사람에 의해 제기된 이 추측은, 주어진 수가 1이 될 때까지 다음 작업을 반복하면,<br>
모든 수를 1로 만들 수 있다는 추측이다..

- 1-1. 입력된 수가 짝수라면 2로 나눔
- 1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더함
- 2 . 결과로 나온 수에 같은 작업을 1이 될 때까지 반복함

입력된 수가 6이라면 6→3→10→5→16→8→4→2→1 이 되어 총 8번 만에 1이 된다.<BR>
이 작업을 몇 번이나 반복해야하는지 반환하는 함수, solution을 완성한다.<br>
작업을 500번 반복해도 1이 되지 않는다면 -1을 반환.<br>

num은 1이상 8000000 미만의 정수

> 입출력 예

|n|result|
|--|--|
|6|8|
|16|4|
|626331|-1|

---

      class Solution {
      public int solution(int num) {
          int answer = 0;
          long n = (long)num;

          //1이 되면 반복 종료
          while(n > 1){
              if(n % 2 == 0){
                  n/=2;
              }else if(n % 2 == 1){
                  n=(3*n)+1;
              }
              answer++;

              if(answer > 500){
                  answer = -1;
                  break;
              }
          }
          return answer;
      }
    }
  
---
