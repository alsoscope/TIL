### CodingTest Level1

정수 num이 양수일 경우 Even 반환, 홀수는 Odd

========================================
class Solution {
  public String solution(int num) {
      String answer = "Odd";
      
      if(num % 2 == 0){
         answer = "Even";
      }      
      return answer;
  }
}
