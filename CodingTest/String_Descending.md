**Coding Test Level1**

## 문자열 내림차순으로 배치하기

- 문자열 s에 나타나는 문자를 큰 것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수 solution 완성하기.<br>
s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주한다.

제한 사항
- s는 길이 1이상인 문자열이다.

입출력 예

|s|return|
|--|--|
|"Zbcdefg"|"gfedbcZ"|

---

    import java.util.Arrays;
    import java.util.Collections;

    class Solution {
      public String solution(String s) {
          String answer = "";

          String[] ss=s.split("");

          //오름차순
          //Arrays.sort(ss);

          //내림차순 정렬
          Arrays.sort(ss, Collections.reverseOrder());

          answer=String.join("", ss);

          return answer;
      }
    }

---

내림차순 배열은 객체의 배열을 이용한다.<br>
Comparator는 정렬 가능한 클래스(Comparable 인터페이스를 구현한 클래스)들의<br>
기본 정렬 기준과 다르게 정렬하고 싶을 때 사용하는 인터페이스이다.<br>
기본적인 정렬 방법인 오름차순 정렬을 내림차순으로 정렬할 때 많이 사용한다.<br>
Comparator는 Collections class의 reverseOrder() 함수를 이용한다.

ref https://jamesdreaming.tistory.com/162


---

    import java.util.Arrays;
    import java.util.Collections;

    class Solution {
      public String solution(String s) {
          String answer = "";

          String[] ss=s.split("");

          //Arrays.sort(ss);

          Collections.reverse(Arrays.asList(ss));

          answer=String.join("", ss);

          return answer;
      }
    }

---

배열을 List로 변환 후 Collections.reverse()를 이용해 역순으로 정렬한다.<br>
Arrays.asList()로 ArrayList를 리턴한다. asList()는 java.util.ArrayList 클래스와는 다른 클래스이다.

---

        import java.util.Arrays;
        import java.util.Collections;

        class Solution {
          public String solution(String s) {
              String answer = "";

              String[] ss = s.split("");
              String tmp;

              //큰 것부터 작은 순으로 내림차순 버블 정렬
              for(int i=0; i<s.length()-1; i++){ //맨끝은 돌아갈 필요가 없으므로 -1
                  for(int j=0; j<s.length()-1-i; j++){
                  //-1-i의 이유는 1회전에서 가장 작은 값이 뒤로 가기 때문. 2회전엔 맨 뒤로 간 수는 비교를 하지 않는다. 맨 뒤에 작은 값이 쌓인다.

                      //j+1이 클 때 바꾼다. s[0]이 s[1]보다 작으면 바꿈. 점점 큰 값이 앞으로 온다.
                      if(ss[j].charAt(0) < ss[j+1].charAt(0)){
                          tmp=ss[j];
                          ss[j]=ss[j+1];
                          ss[j+1]=tmp;
                      }
                  }
              }

              answer=String.join("", ss);

              return answer;
          }
        }

---

- 문자열을 나누는 메소드
    1. public String[] split(String regex)
    2. public String[] split(String regex, int limit)
    
    regex : 문자열을 나누기 위한 정규표현식 <br>
    limit : 분류할 문자열의 수

- 문자열을 합치는 메소드<br>
    반복되는 구분자를 이어줄 때 : 일일이 _ 를 붙인다, for문 사용, String.join 사용.

    String.join 메소드

 - public static String join(CharSequence delimiter, CharSequence... elements)
 
        example
        String msg=String.join("-", "Java", "is", "cool");
        //msg returned is : "Java-is-cool"

delimiter : 구분자 <br>
elements : 결합할 요소들

Note that if an element is null, then "null" is added.<br>
Parameters:
delimiter - the delimiter that separates each element<br>
elements - the elements to join together.<br>
Returns:
a new String that is composed of the elements separated by the delimiter<br>
Throws:
NullPointerException - If delimiter or elements is null
    
