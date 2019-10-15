게시판에서 게시글의 제목/작성자/내용에 속할 수 있는 검색을 시도할 때

화면 검색에 필요한 화면

	<form id="form1" method="post">
		<div style="text-align:center;">
			<select name=searchType><!-- eq (==) -->
				<option value="n"
					<c:out value="${cri.searchType == null ? 'selected':'' }"/>>검색 구분</option>
			<option value="t"
					<c:out value="${cri.searchType eq 't' ? 'selected':'' }"/>>Title</option>
	...
			</select>
		<input type="text" name="keyword" id="keywordInput" placeholder="검색어 입력" value="${cri.keyword }">
		<input type="submit" class="btn btn-default" value="검색">
		</div>
	</form>


boardMapper.xml

	<sql id="search">
			<if test="searchType != null">
				<if test="searchType == 't'.toString()">
					and title like CONCAT('%', #{keyword}, '%')
				</if>
				<if test="searchType == 'tc'.toString()">
					and (title like CONCAT('%', #{keyword}, '%') OR content like CONCAT('%',#{keyword},'%'))
				</if>
				...
			</if>
	</sql>

반복되는 구절, 동적 쿼리를 생성한다. 각 태그에 <sql refid=""> id 값을 기입해 사용.

MySQL LIKE문. 문자열 합치는 함수.<br>
WHERE(AND) column LIKE CONCAT('%', #{keyword}, '%')<br>
column은 검색할 필드명, 검색할 내용은 '%', '%' 사이에서 해당되는 문자열을 찾는다.<br>
