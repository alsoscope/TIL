map 인터페이스<br>
Guava Cache

- put

- containsKey()<br>
이 메소드는 map에 해당 key가 있는지 조사하여 그 결과값을 리턴한다.

- 캐시에서 키와 관련된 값 가져오는 메소드

  - getUnchecked()<br>
  note that we're using the getUnchecked() operation – this computes and loads the value into the cache if it doesn't already exist.

ref https://ijbgo.tistory.com/10
