### CollectionsFramework
 - ArrayList의 사용법


        import java.util.ArrayList;

        class Main {

            public static void main(String[] args) {
                String[] arrayObj = new String[2];
                arrayObj[0] = "one";
                arrayObj[1] = "two";
                //arrayObj[2] = "three"; 오류가 발생한다.
                for(int i=0; i<arrayObj.length; i++){
                    System.out.println(arrayObj[i]);
                }

                ArrayList al = new ArrayList();
                al.add("one");
                al.add("two");
                al.add("three");

                //구식
                for(int j=0; j<al.size(); j++){
                  String value=(String)al.get(j);//Object 타입이므로, String으로 형변환해준다.
                  System.out.println(value);
                }

                //제너릭. 타입의 안정성 확보. al이라는 arraylist에 추가되는.add() 값이 string 데이터 타입이다.
                //값을 가져올get() 때 (String)으로 형변환하지 않아도 됨.
                ArrayList<String> al=new ArrayList<String>();	

                //size(), get() 메소드로 배열 값을 다룬다.
                // for(int i=0; i<al.size(); i++){
                //     System.out.println(al.get(i));
                // }
            }
        }
        
ref https://edu.goorm.io/learn/lecture/41/%EB%B0%94%EB%A1%9C%EC%8B%A4%EC%8A%B5-%EC%83%9D%ED%99%9C%EC%BD%94%EB%94%A9-%EC%9E%90%EB%B0%94-java/lesson/39156/arraylist%EC%9D%98-%EC%82%AC%EC%9A%A9%EB%B2%95

https://galgum.tistory.com/18


## List 와 ArrayList의 차이

List list = new ArrayList();<br>
ArrayList list = new ArrayList();

- 자바의 다형성<br>
List 인터페이스에 상속된 클래스인 ArrayList, LinkedList... 등이 있다.

- ArrayList 정렬<br>
Collections.sort() 메소드를 사용한다.
