MySQL Stored Procedure / VIEW 보안 설정으로 접근 제어 설정.

    CREATE OR REPLACE DEFINER = {`user`@`CURRENT_USER`}
    SQL SECURITY DEFINER VIEW `[데이터베이스]`.`[테이블명]`

    ( `a`, `b` ... ) AS SELECT `[테이블 alias]`.`[column]` AS `[column alias]`, `testb`.`B` AS `B` ....
    FROM (((`[데이터베이스]`.`[테이블명]` `[테이블 alias]` 
    JOIN `[데이터베이스]`.`[테이블명]` `B` ON (`[테이블 alias]`.`[column]` = `B`.`BCD`))
    ))

SQL SECURITY DEFINER : 생성한 user의 권한을 따름

JOIN의 ON절<br>
WHERE절과 비교했을 때, 범위가 다르기에 결과도 달라진다.

