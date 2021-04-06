MySQL 인덱스 설정

- 테이블 CREATE 할 때 인덱스 생성

<pre>
<code>
  ~~
   UNIQUE KEY `capId_UNIQUE`(`trxId`),
   PRIMARY KEY(`trxId`),
   INDEX `ix_trx_realtime_pay_mchtId`(`mchtId`),
   INDEX `ix_trx_realtime_pay_tmnId`(`tmnId`),
  ~~
</code>
</pre>

- 인덱스 추가

<pre>
<code>
ALTER TABLE `테이블명` ADD INDEX `인덱스명` (`컬럼명`);
</code>
</pre>


- 인덱스 보기

<pre>
<code>
show index from 테이블명;
</code>
</pre>
