## Foreign Key 외래키 (외부키, 참조키, 외부 식별자, 외래키 라고도 한다.)

위키피디아 : 관계형 데이터베이스(RDB)에서 외래 키(외부 키, Foreign Key)는 한 테이블의 필드(attribute) 중, <br>
다른 테이블의 행(row)을 식별할 수 있는 키를 말함. 다른 테이블의 기본 키를 참조한다.

FK가 정의된 테이블이 자식 테이블 Child Table<br>
외래키로 참조되는 테이블을 부모 테이블이라 함 Parent Table

참조되는 컬럼은 PK나 UK(Unique Key)여야 한다.<br>
외래키와 참조되는 컬럼의 데이터 타입이 일치해야 한다.

일반적으로 데이터베이스를 설계할 때,<br>
자식 테이블의 FK 컬럼은 부모 테이블의 참조하는 컬럼과 같은 이름을 사용.<br>
다른 이름을 사용해도 무관하지만, 되도록 같은 이름을 사용하는 것이<br>
테이블 간의 관계를 한 번에 알아볼 수 있음

- foreign key 설정

      create table 테이블(
      ...
      CONSTRAINT [제약조건명] FOREIGN KEY(컬럼)
      REFERENCES [참조할 테이블](참조할 컬럼명)
      [ON DELETE CASCADE / ON UPDATE CASCADE]
      );

또는

      create table 테이블(
      ...
      FOREIGN KEY(참조하는 테이블의 컬럼명)
      REFERENCES [참조되는 테이블]
      [ON DELETE CASCADE / ON UPDATE CASCADE]
      );
      
또는 

      ALTER TABLE [추가할 테이블] add constraint [제약조건명] foreign key(컬럼명)
      references [부모테이블명](PK컬럼명) [ON DELETE CASCADE / ON UPDATE CASCADE];

ON DELETE CASCADE : 외래 키에서 참조하는 키가 포함된 행을 삭제하려고 하면 해당 외래 키가 포함된 모든 행도 삭제<br>
ON UPDATE CASCADE : 외래 키에서 참조하는 키가 포함된 행에서 키 값을 업데이트하면 해당 외래키를 구성하는 모든 값도 업데이트

- foreign key 삭제

      ALTER TABLE [child 테이블명] DROP FOREIGN KEY [제약조건명];

- foreign key 확인
   - 테이블 기준 확인

          select * from information_schema.table_constraints where table_name = '테이블명';

   - 데이터베이스 기준 확인

          select * from information_schema.table_constraints where constraint_schema = '데이터베이스명';

외래 키의 모든 필드의 값은 참조되어지는 Parent Table의 기본 키 값과 동일하거나 NULL이어야 한다.

자식 테이블에 데이터를 insert 하려고 할 때, 부모 테이블의 참조하는 컬럼에 없는 값을 삽입하면<br>
Intergrity Constraint 오류가 발생함.<br>
(부모테이블의 참조 되어지는 컬럼에 존재하는 값만을 입력할 수 있음)

참조되어지는 부모 테이블을 삭제하려면 에러가 발생한다.<br>
DROP TABLE [테이블명]; //참조 무결성 에러

(외래키가 포함된)참조하는 테이블인 Child Table을 먼저 삭제하거나,

FK를 삭제하거나,
Parent Table에 CASCADE CONSTRAINTS 옵션을 통해 삭제한다.

      DROP TABLE [테이블명] CASCADE CONSTRAINTS;


ref http://blog.naver.com/PostView.nhn?blogId=aristort&logNo=2018567288
