https://datatables.net/ 의 DataTables는 HTML table을 다루는 jQuery Javascript 라이브러리이다.
  
회원목록 테이블에 사용하기 위해 CDN에서 jQuery, dataTables.css, js를 받아왔지만<br>
개발자 도구에서 type error, DataTable() is not a function... 이라는 에러로 적용이 되지 않자<br>
이를 해결하기 위해 알아보던 중<br>
jQuery를 사용할 때 다른 라이브러리들 / jQuery버전과 충돌하는 경우임을 알게됨.

1. 다른 라이브러리와 충돌
	- jQuery의 alias인 $.noConflict();로 표기할 수 있지만,<br>
다른 라이브러리에서 $를 함수나 변수로 사용한다면 jQuery가 제대로 작동하지 않을 수 있기에
$를 alias로 사용하지 않거나, var data=jQuery.noConflict(); 같이 data를 jQuery의 alias로 사용한다.

			<script>
				jQuery.noConflict();

				$(document).ready( function () {
					$('#myTable').DataTable();
				} );
			</script>
		
2. 다른 버전의 jQuery와 충돌
	- 버전 별로 alias를 다르게 지정한다.

ref https://www.codingfactory.net/10795
