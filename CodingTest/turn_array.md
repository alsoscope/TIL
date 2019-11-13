**Coding Test Level1**

## 자연수 뒤집어 배열로 만들기

- 자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴.<br>
예를들어 n 이 12345 이면 [5,4,3,2,1] 을 리턴한다.

제한조건
- n은 10,000,000,000이하인 자연수

입출력 예

|n|return|
|---|---|
|12345|[5,4,3,2,1]|

---

    class Solution {
      public int[] solution(long n) {

          //long타입 변수 n에 담긴 문자열을 String 문자열로 선언.
          String nStr=new String(n+"");

          //toCharArray로 문자열을 쪼개 char[] 배열 temp에 저장
          char[] temp=nStr.toCharArray();

          //배열 answer를 글자수 길이만큼 할당.
          int[] answer = new int[temp.length];

          //Integer.parseInt로 문자열을 숫자로 변환.
          //배열을 거꾸로 뒤집어 return한다.
          for(int i=0; i<temp.length; i++){
              answer[i]=Integer.parseInt(temp[temp.length-1-i]+"");
          }

          return answer;
      }
    }

---
