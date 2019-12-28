## 시저 암호

- 어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식 : `시저 암호`<br>
예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 되고, "z"는 1만큼 밀면 "a"가 된다.

문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution 완성 하기.

|s|n|result|
|--|--|--|
|"AB"|1|"BC"|
|"z"|1|"a"|
|"a B z"|4|"e F d"|

- 제한 조건
  - 공백은 아무리 밀어도 공백이다.
  - s는 알파벳 소문자, 대문자, 공백으로만 이루어짐.
  - s의 길이는 8000이하이다.
  - n은 1 이상, 25 이하인 자연수이다.

---

    class Solution {
      public String solution(String s, int n) {
          String answer = "";

          for(int i=0; i<s.length(); i++){
              char str = s.charAt(i);

              if(str != ' '){
                  char start=Character.isLowerCase(str) ? 'a' : 'A';
                  str=(char)(start + (str+n-start) % 26);
              }
              answer+=str;
          }
          return answer;
      }
    }

---

    class Solution {
      public String solution(String s, int n) {
          String answer = "";

          int num=0;
        char[] arr=new char[s.length()];

        while(n > 26) {
          n=n-26;
        }

        for(int i=0; i<s.length(); i++) {
          if(s.charAt(i) >= 'A' && s.charAt(i) <= 'Z') {
            if((int)s.charAt(i) + n > 'Z')
              num=(int)s.charAt(i)+n-26;
            else
              num=(int)s.charAt(i)+n;
            arr[i]=(char)num;
          }else if(s.charAt(i) >= 'a' && s.charAt(i) <= 'z'){
            if((int)s.charAt(i) + n > 'z')
              num=(int)s.charAt(i)+n-26;
            else
              num=(int)s.charAt(i)+n;
            arr[i]=(char)num;
          } else {
            arr[i]=s.charAt(i);
          }
          answer+=arr[i];
        }
          return answer;
      }
    }

---

    class Solution {
      public String solution(String s, int n) {
          int ascii[]=new int[s.length()];
        char chars[]=new char[s.length()];

        //StringBuilder 클래스. 변경할 수 있는 문자열을 나타낸다.
        StringBuilder answer=new StringBuilder();

        for(int i=0; i<chars.length; i++) {
          chars[i]=s.charAt(i);

          //대문자일 경우 ASCII 코드 기준 A=65, Z=90
          if(chars[i] > 64 && chars[i] < 91) {
            ascii[i]=chars[i]+n;

            if(ascii[i] > 90) {
              ascii[i]-=26;
            }
          //소문자일 경우 ASCII 코드 기준 a==97, z==122
          }else if(chars[i] > 96 && chars[i] < 123) {
            ascii[i]=chars[i]+n;

            if(ascii[i]>122) {
              ascii[i]-=26;
            }
          } else if(chars[i] == 32) {
            //공백일 경우
            //ASCII 코드 기준 공백(space) = 32
            ascii[i]=32;

            //char를 StringBuilder로 합친다
          }	
          answer.append(Character.toString((char) ascii[i]));
        }
        return answer.toString();
      }
    }
