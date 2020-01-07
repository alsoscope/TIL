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
