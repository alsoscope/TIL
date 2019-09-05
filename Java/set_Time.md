### datetime, timestamp
MySQL에서 사용하는 날짜를 다루는 데이터 자료형에 대해서.

MySQL에는 이미 날짜 기입에 사용할 수 있는 여러가지 내장 함수가 있다.

기존에 사용했던 게시물 등록시 생성되는 날짜 함수

> regdate timestamp not null default CURRENT_TIMESTAMP

timestamp / datetime : 두 자료형 다 데이터를 다루지만, 차이점이 있다.

### 1)지원되는 범위

- datetime 1000-01-01 00:00:00 ~ 9999-12-31 23:59:59 까지
- timestamp 1970-01-01 00:00:00 ~ 2037-12-31 23:59:59 까지

### 2)데이터베이스에 저장될 때
- datetime은 문자형 String
- timestamp는 숫자형 int로 변환되어 저장된다

### 3)저장되는 공간의 크기
- datetime 8byte
- timestamp 4byte

### 4)자동입력 여부
- datetime은 수정할 일이 있으면 그때마다 날짜를 입력해야 한다
- timestamp는 날짜를 따로 입력안해도 자동으로 입력 가능. (CURRENT_TIMESTAMP 사용시)

예를 들어, 등록일에는 datetime을, 수정할 때는 timestamp를 사용하면 일일이 수정일시를 입력하지 않아도 될 것

### 5) index/ 조회 캐쉬
- datetime : index 불가능 / 조회 캐쉬 안됨
- timestamp : index 가능 / 조회 캐쉬 됨

### 6) 서버 timezone
- datetime : 서버 timezone 변경시 시간 변동 없음
- timestamp : 서버 timezone 변경시 시간 변동

---

regist DATETIME DEFAULT CURRENT_TIMESTAMP<br>
현재 Timestamp 값을 insert 시점에 기본값으로 set한다<br>
이때, update필드에는 null값이 들어감<br>

update DATETIME ON UPDATE CURRENT_TIMESTAMP<br>
해당 row가 update될 경우 자동으로 해당 시점의 timestamp값으로 set된다<br>

regist timestamp default current_timestamp<br>
update timestamp on update current_timestamp<br>

regist를 하면 update 필드에 0000-00-00 00:00:00로 등록됨, update를 하면 자동으로 시간이 업데이트된다


ref https://devx.tistory.com/entry/datetime%EA%B3%BC-timestamp%EC%9D%98-%EC%B0%A8%EC%9D%B4 http://blog.breakingthat.com/2018/03/16/mysql-%EC%BB%AC%EB%9F%BC-default-%EC%84%A4%EC%A0%95-datetime/
http://linux.systemv.pe.kr/timestamp-datetime-%EA%B8%B0%EB%8A%A5-%EA%B0%9C%EC%84%A0/
http://blog.daum.net/_blog/BlogTypeView.do?blogid=03aaf&articleno=12379936&_bloghome_menu=recenttext
