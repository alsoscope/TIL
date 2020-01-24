### DB에서 가져온 Timestamp를 자바에서 가공하여 JSP로 출력하기

자바에서 Timestamp형 Date를 String 변수에 담으면 된다.

.class

    String insertDate=dto.getInsertDate();

.jsp

    <%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>

    <!-- parseDate로 String → Date 형 변환 -->
    <fmt:parseDate value="${list.insertDate }" var="insertDate" pattern='yyyy-MM-dd'></fmt:parseDate>

    <!-- 숫자로 변환된 두 데이터를 연산 후 formatNumber 등으로 원하는 포맷과 단위로 화면에 출력 -->
    <td><fmt:formatDate value="${insertDate }" pattern='yyyy-MM-dd'/>일</td>

fmt(Formatting Tags) 태그 : 서버에서 받은 데이터를 JSP페이지에서 날짜, 시간을 계산하여 화면에 뿌려줌.<br>
(자바 스크립트를 사용해도 되지만 서버단에서 안전하게 처리할 수 있다.)

<fmt:formatDate> : 날짜 정보를 담고 있는 객체를 포맷팅하여 출력할 때 사용하는 태그<br>
<fmt:parseDate> : 문자열로 표시된 날짜 및 시간 값을 java.util.Date로 파싱해주는 태그

<fmt:parseDate>로 String → Date 형변환<br>
<fmt:parseNumber>를 이용하여 Date → Number 변환<br>
숫자로 변환된 두 데이터를 연산 후 <fmt:formatNumber>등을 이용하여 원하는 포맷과 단위로 화면에 출력

#### DB에서 가져온 날짜를 가공해서 JSP에 뿌려주기

        //insert한 날짜에 amount만큼 더한 날짜 exprDate 구하기
		//SimpleDateFormat 인스턴스로 날짜를 원하는 패턴으로 출력하기
		SimpleDateFormat f=new SimpleDateFormat("yyyy-MM-dd");
		
		//---------------------------------------현재시간 확인
		Calendar cal=Calendar.getInstance();
		cal.setTime(new Date());
		System.out.println("insertDate : " + f.format(cal.getTime()));	
		//---------------------------------------------------------------
        
        int amount=vo.getAmount();
		System.out.println("insert amount : " + amount);
		
		//Calendar 인스턴스 생성
		Calendar expr=Calendar.getInstance();
		
		for(int i=1; i<=10; i++) {
			if(amount==i) {
				//Date 인스턴스만 format 메소드에 사용될 수 있다. Calendar 인스턴스를 Date 인스턴스로 변환하기.
				expr.setTime(new Date());//new Date로 Date 객체 생성
				expr.add(expr.DATE, amount);
				
				/*System.out.println(f.format(expr.getTime()));*/
				String exprDate=f.format(expr.getTime());//출력용으로 Date 클래스를 얻는다.
				System.out.println("exprDate : " + exprDate);
				dto.setExprDate(exprDate);
			}
		}

		cartService.insertOrder(dto);
        
DB에는 String으로 저장되기에 list를 뽑아 fmt 포맷으로 찍으면 NULL이 나온다.<br>
Date형으로 INSERT해서 SELECT 할 때 String으로 변환하여 화면에 출력해야함.
