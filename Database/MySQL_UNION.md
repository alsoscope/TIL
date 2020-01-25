## MySQL UNION 쿼리

여러 테이블에서 같은 결과를 얻어야 할 때 사용할 수 있다.<br>
컬럼명은 달라도 데이터 형식이 호환되면 UNION으로 결과를 얻어낼 수 있다.

UNION은 중복을 포함하지 않는다.
UNION ALL은 중복을 포함한다.

cartMapper.xml

    (SELECT c.cartId, c.userId, p.product_id, m.userName, p.product_name, c.amount, 
			   p.product_price, (product_price * amount) money
		FROM tbl_member m, tbl_product p, tbl_cart c
		WHERE m.userId = c.userId
			AND p.product_id=c.product_id
			AND c.userId = #{userId}
		)
		
		UNION
		
		(SELECT c.cartId, c.userId, p.product_id, m.userName, p.product_name, c.amount, 
			   p.product_price, (product_price * amount) money
		FROM tbl_member m, tbl_product_abroad p, tbl_cart c
		WHERE m.userId = c.userId
			AND p.product_id=c.product_id
			AND c.userId = #{userId}
		)
		
		UNION
		
		(SELECT c.cartId, c.userId, p.product_id, m.userName, p.product_name, c.amount, 
			   p.product_price, (product_price * amount) money
		FROM tbl_member m, tbl_product_etcetera p, tbl_cart c
		WHERE m.userId = c.userId
			AND p.product_id=c.product_id
			AND c.userId = #{userId}
		)


ref https://link2me.tistory.com/750

