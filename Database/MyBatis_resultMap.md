MyBatis xml파일에서 설정하는 ResultMap이란,<br>
DB 필드명과 DTO 객체의 변수명(property)이 다를 때 사용.

<resultMap id="" .. 에는 임의의 이름을, .. type=""> 에는 DTO 명을 명시한다.<br>
<result property="" .. 에는 DTO 변수명(property)을, ..column=""> 에는 DB 필드명을 명시.

- 사용
  - mybatis_config.xml

        <mapper namespace="com.p.project">
          <resultMap id="etcResult" type="ProductDTO">
              <result property="product_id" column="etc_item_id"/>
              <result property="product_price" column="etc_item_price"></result>
              <result property="product_desc" column="etc_item_desc"></result>
          </resultMap

          <select id="productInfo" resultMap="etcResult">
            select * from tbl_etc order by product_id
          </select>
        </mapper>
