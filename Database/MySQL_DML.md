### DML (SELECT, INSERT, UPDATE, DELETE)
데이터 조작어

  - __데이터명 변경__<br>
  UPDATE [테이블명] SET [필드명]=[변경할 데이터명] WHERE [필드명]=[데이터명];<br>
  update tbl_product set product_name='ASAKO' where product_name="ASSAKO";

  - __최근 N개의 데이터 출력__<br>
  SELECT [칼럼1], [칼럼2..] FROM [테이블명] ORDER BY [기준이 되는 컬럼] DESC LIMIT 10; (10개의 데이터 출력)


