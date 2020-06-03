MySQL ZEROFILL

       aaa          INT(10) UNSIGNED ZEROFILL NULL DEFAULT NULL,
       bbb          DECIMAL(10, 2) UNSIGNED ZEROFILL NULL DEFAULT NULL,

   ZEROFILL 옵션이 있는 데이터들은<br>
   자릿수가 괄호 안의 수보다 작을 때 자릿수를 다 0으로 채운다
   
   int(11) zerofill 옵션을 붙이고<br>
   1, 1234567890, 123456을 INSERT 하면
   
       00000000001
       01234567890
       00000123456

   출력
