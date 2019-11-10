**CodingTest Level1**

## 정수 내림차순으로 배치하기

함수 solution은 정수 n을 매개변수로 입력받는다. n의 각 자릿수를 큰 것부터 작은 순으로 정렬한 새로운 정수를 리턴한다.<br>
예를들어 n이 118372면 873211을 리턴한다.

- n은 1이상 8,000,000,000 이하의 자연수.

|n|return|
|--|--|
|118372|873211|

---

    import java.util.Arrays;

    class Solution {
      public long solution(long n) {
          long answer = 0;

          String[] nArr = String.valueOf(n).split(""); 
          Arrays.sort(nArr);

          String nStr=new String("");
          for(int i = nArr.length-1; i>=0; i--){
              nStr += nArr[i];
              answer=Long.parseLong(nStr);
          }
          return answer;
      }
    }

---
