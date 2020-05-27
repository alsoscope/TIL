String 클래스는 불변 객체(Immutable Object)이다. 값을 바꿀 수 없음.
값을 바꾼다면 매번 생성되기에, 가비지 콜렉터가 호출되기 전까지 주소값은 stack, string 클래스는 heap 영역에 쌓인다.

    String str1="";
    String str2="";

    System.out.println(str1 + str2);
    //aabb

String class의 내부 구조는 final형이기 때문에 초기값으로 주어지면 바꿀 수 없다.

'+' 연산자를 통해 더할 수 있지만
이처럼 string 객체를 직접 더하는 것보다 StringBuilder, StringBuffer를 사용한다.

>Strings are constant; their values cannot be changed after they are created.
String buffers support mutable strings.
Because String objects are immutable they can be shared.

The Java language provides special support for the string concatenation operator ( + ),
and for conversion of other objects to strings.
String concatenation is implemented through the StringBuilder(or StringBuffer) class and its append method.
String conversions are implemented through the method toString, defined by Object and inherited by all classes in Java

Concatenation Operator (||)
자바에서의 concat 명령어와 유사하다.

문자열을 연결해준다. 연산자.

StringBuffer, StringBuilder는 메모리에 append 되는 방식이다. 문자열의 저장 및 변경을 위한 메모리 공간을 가지고 있다.
append와 insert 메소드.

- StringBuffer와 StringBuilder의 차이점

  - StringBuilder - synchronization 적용하지 않아서 동시에 처리하는 것을 허용하지 않기에 단일 스레드 환경에서만 사용 가능.
  StringBuffer보다 좀 더 빠른 성능을 보인다.
  - StringBuffer - thread-safe. multiple thread 환경에서 안전한 클래스. 동시에 처리하는 것을 허용한다.

ref https://novemberde.github.io/2017/04/15/String_0.html
