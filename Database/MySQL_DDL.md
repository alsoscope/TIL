### DDL (CREATE, ALTER, DROP, RENAME, TRUNCATE)
`데이터 제어어`

  - 데이터베이스 생성<br>
  CREATE DATABASE [DB명];

  - 데이터베이스 삭세<br>
  DROP DATABASE [DB명];
  
  - 테이블 이름 수정<br>
  RENAME TABLE 테이블명 TO 새테이블명;
  ALTER TABLE 테이블명 RENAME [새테이블명];
  
  - 컬럼명 변경<br>
  ALTER TABLE 테이블명 CHANGE 기존컬럼명 새컬럼명 자료형(길이);<br>
  alter table tbl_admin change admin_email admin_name varchar(10);  
 
  - 필드 삭제<br>
  ALTER TABLE [테이블명] DROP [필드명];<br>
  alter table tbl_product drop product_url;
 
  - 컬럼 추가<br>
  ALTER TABLE [테이블명] ADD [컬럼명][타입][옵션];<br>
  alter table [테이블명] add[컬럼명] varchar(100) not null default '0';
 
  - 컬럼타입 수정<br>
  ALTER TABLE [테이블명] MODIFY [컬럼명] 자료형(길이);
  
  - 테이블 삭제<br>
  DROP TABLE [테이블명];
   
  ---

  - __제약 조건 추가__ (삭제, 갱신의 제약을 걸어 부모-자식 테이블에 CASCADE 적용)<br>
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
  
  ---
  
**DCL** (GRANT, REVOKE) : 데이터 제어어

__TCL__ (COMMIT, ROLLBACK, SAVEPOINT) : Transaction Control Language
