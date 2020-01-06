### DML (SELECT, INSERT, UPDATE, DELETE)
데이터 조작어

  - 데이터명 변경<br>
  UPDATE [테이블명] SET [필드명]=[변경할 데이터명] WHERE [필드명]=[데이터명];<br>
  update tbl_product set product_name='ASAKO' where product_name="ASSAKO";

  - 필드 삭제<br>
  ALTER TABLE [테이블명] DROP [필드명];<br>
  alter table tbl_product drop product_url;

  - 최근 N개의 데이터 출력<br>
  SELECT [칼럼1], [칼럼2..] FROM [테이블명] ORDER BY [기준이 되는 컬럼] DESC LIMIT 10; (10개의 데이터 출력)

  - 제약 조건 추가 (삭제, 갱신의 제약을 걸어 부모-자식 테이블에 CASCADE 적용)<br>
  ALTER TABLE [추가할 테이블] ADD CONSTRAINT [제약조건명] FOREIGN KEY(필드명)<br>
  REFERENCES [부모테이블명] (PK필드명) [ON DELETE CASCADE ON UPDATE CASCADE];
  
  - 기본키 제약조건<br>
  ALTER TABLE [테이블명] ADD CONSTRAINT [제약조건명] PRIMARY KEY(컬럼명);
  
  - NOT NULL 제약조건 추가<br>
  ALTER TABLE [테이블명] MODIFY [컬럼명] [데이터타입] CONSTRAINT [제약조건명] NOT NULL;
  
  - 제약조건 (RESTRICT 제거)<br>
  ALTER TABLE [테이블명] DROP CONSTRAINT [제약조건명];
  
  - 외래키 제약조건 제거<br>
  ALTER TABLE [child 테이블명] DROP FOREIGN KEY [제약조건명];
  
### DDL (CREATE, ALTER, DROP, RENAME, TRUNCATE)
데이터 제어어

  - 데이터베이스 생성<br>
  CREATE DATABASE [DB명];

  - 데이터베이스 삭세<br>
  DROP DATABASE [DB명];
  
  - 테이블 이름 변경<br>
  RENAME TABLE 테이블명 TO 새테이블명;
  
  - 컬럼명 변경<br>
  ALTER TABLE 테이블명 CHANGE 기존컬럼명 새컬럼명 기존자료형(새자료형);<br>
  alter table tbl_admin change admin_email admin_name varchar(10);  
  
 
**DCL** (GRANT, REVOKE) : 데이터 제어어

__TCL__ (COMMIT, ROLLBACK, SAVEPOINT) : Transaction Control Language
