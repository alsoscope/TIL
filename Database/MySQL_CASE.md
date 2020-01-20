    mysql> select * from tbl_order;
    +--------+--------+------------+--------+---------------------+--------------+--------+---------------------+
    | cartId | userId | product_id | amount | insertDate          | product_name | allSum | exprDate            |
    +--------+--------+------------+--------+---------------------+--------------+--------+---------------------+
    |     10 | cc     |         15 |      1 | 2020-01-08 17:47:11 | 1            |    501 | 2020-01-15 20:34:18 |
    |     11 | cc     |         16 |      1 | 2020-01-08 19:32:00 | ds           |    555 | 2020-01-15 20:34:18 |
    |     12 | dd     |         17 |      1 | 2020-01-15 20:41:38 | rr           |    544 | 2020-01-15 20:41:38 |
    +--------+--------+------------+--------+---------------------+--------------+--------+---------------------+
    3 rows in set (0.00 sec)

    mysql> SELECT IF (amount = 1, exprDate + interval 1 day, NULL)FROM tbl_order;
    +--------------------------------------------------+
    | IF (amount = 1, exprDate + interval 1 day, NULL) |
    +--------------------------------------------------+
    | 2020-01-16 20:34:18                              |
    | 2020-01-16 20:34:18                              |
    | 2020-01-16 20:41:38                              |
    +--------------------------------------------------+
    3 rows in set (0.02 sec)

`+ INTERVAL 1 DAY` : 설정한 시간에서 요일을 하루 더한다.

### MySQL CASE 사용법

    CASE
      WHEN 조건
      TEHN '반환값'
      ELSE 'WHEN 조건에 해당 안되는 경우 반환값'
    END

    <select id="selectExprDate" resultType="com.p.project.DTO.OrderDTO">
        SELECT exprDate, 
          case
            when amount = 1 then exprDate + interval 1 day
            when amount = 2 then exprDate + interval 2 day
            when amount = 3 then exprDate + interval 3 day
          end
        FROM tbl_order
      </select>

    <select id="selectExprDate" resultType="com.p.project.DTO.OrderDTO">
      SELECT exprDate, amount FROM tbl_order WHERE userId=#{userId}
        <choose>
          <when test="amount == 1">
            AND exprDate + interval 1 day
          </when>
          <when test="amount == 2">
            AND exprDate + interval 2 day
          </when>
          <when test="amount == 3">
            AND exprDate + interval 3 day
          </when>
        </choose>
    </select>
