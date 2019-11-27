## Foreign Key 외래키



- foreign key 추가

      alter table [추가할 테이블] add constraint [제약조건명] foreign key(컬럼명)
      references [부모테이블명](PK컬럼명) [ON DELETE CASCADE / ON UPDATE CASCADE];

또는

      create table 테이블(
      ...
      constraint [제약조건명] foreign key(컬럼)
      references [참조할 테이블](참조할 컬럼명)
      [ON DELETE CASCADE / ON UPDATE CASCADE]
      );

ON DELETE CASCADE : 외래 키에서 참조하는 키가 포함된 행을 삭제하려고 하면 해당 외래 키가 포함된 모든 행도 삭제<br>
ON UPDATE CASCADE : 외래 키에서 참조하는 키가 포함된 행에서 키 값을 업데이트하면 해당 외래키를 구성하는 모든 값도 업데이트

- foreign key 삭제

      alter table [테이블명] drop foreign key [제약조건명];

- foreign key 확인
   - 테이블 기준 확인

          select * from information_schema.table_constraints where table_name = '테이블명';

   - 데이터베이스 기준 확인

          select * from information_schema.table_constraints where constraint_schema = '데이터베이스명';
