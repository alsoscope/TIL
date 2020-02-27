**Coding Test Level1**

## 문자열 내 p와 y의 개수

- 대문자와 소문자가 섞여있는 문자열 s가 있다ㅣ s에 'p'의 개수와 'y'의 개수를 비교해 같으면 true, 다르면 false를 리턴하는 solution 완성하기.<br>
'p', 'y' 모두 하나도 없는 경우는 항상 true를 리턴한다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않는다.

예를 들어 s가 "pPoooyY"면 true 리턴, "Pyy"면 false를 리턴한다.

제한사항
- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있다.

입출력 예
|s|return|
|--|--|
|"pPoooyY"|true|
|"Pyy"|false|

---

        class Solution {
        boolean solution(String s) {
            boolean answer = true;

            int p = 0;
            int y = 0;

            // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
            System.out.println("Hello Java");

            for(int i=0; i<s.length(); i++){
                if(s.charAt(i)=='p')    {
                    p++;
                } else if (s.charAt(i)=='y'){
                    y++;
                }
            }

            if(p!=y)
                answer=false;

            return answer;
        }
    }

---
