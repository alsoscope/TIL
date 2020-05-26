Oracle 설치 후

    >sqlplus scott/tiger
    
SCOTT, HR은 오라클에서 제공하는 샘플 user 계정이다.

### user
- SYS, SYSTEM<br>
암호는 설치시 지정. 

    #### SYS
    oracle DB 관리자. 최상위 관리자.<br>
    관리자 권한으로 오라클 접속. 데이터베이스의 모든 설정 가능.

    #### SYSTEM
    권한은 SYS와 동일하지만 DB를 생성할 수 있는 권한이 없다.

      >sqlplus "/as sysdba"
      또는
      >sqlplus as / sysdba

      SQL> show user

      USER은 "SYSTEM"입니다
    
- 오라클 계정 생성

      >sqlplus as/ sysdba

- 테이블 스페이스 만들기

  - Table Space란<br>
    테이블 및 인덱스를 저장해놓은 오라클의 논리적 공간.<br>
    실제 물리적 공간은 데이터 파일이다. (확장자.DBF)<br>
    테이블 스페이스의 관리는 관리자만 가능하다.

SQL PLUS를 실행시키고 System user로 로그인한다.

    create tablespace [테이블 스페이스명]
    datafile 'c:\_dev\oracle_user' --파일경로
    size 50m --초기 데이터 파일 크기 설정
    autoextend on next 10m --초기 크기 공간을 모두 사용하는 경우 자동으로 파일의 크기가 커지는 기능
    maxsize 100m; --데이터 파일이 최대로 커질 수 있는 크기 지정. 기본값=unlimited

    SQL> create tablespace oracle
      2  datafile 'c:\_dev\oracle_user' size 50m
      3  autoextend on
      4  next 10m
      5  maxsize unlimited;

    테이블스페이스가 생성되었습니다.

- 사용자 계정 생성

      create user java identified by java1234
      default tablespace oracle;

      사용자가 생성되었습니다.

- user에 권한 부여
  - SYS 관리자 계정 접속
  
        connect /as sysdba

        SQL> grant connect, resource, dba to java;

        grant connect, resource to [유저];

        권한이 부여되었습니다.

        C:\Users\mtouch>sqlplus

        SQL*Plus: Release 19.0.0.0.0 - Production on 화 5월 26 16:14:28 2020
        Version 19.3.0.0.0

        Copyright (c) 1982, 2019, Oracle.  All rights reserved.

        사용자명 입력: java
        비밀번호 입력:

        다음에 접속됨:
        Oracle Database 19c Enterprise Edition Release 19.0.0.0.0 - Production
        Version 19.3.0.0.0

- 로그인 없이 sqlplus 접속

        >sqlplus /nolog

        >connect scott/tiger
        >conn scott/tiger
        //오라클 설치시 기본적으로 생성되는 계정.

        >connect/ as sysdba
        >conn / as SYSDBA
    
ref https://heavenly-appear.tistory.com/98
