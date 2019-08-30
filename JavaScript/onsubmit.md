onsubmit

	<form onsubmit="return checkValidation()" action="/login">
	</form>
	<input type="submit>

form 태그 안에서 form 전송을 하기 전에 입력된 데이터의 유효성을 체크하기 위해 사용하는 이벤트

checkValidation()의 리턴값을 form에 전달해야 한다

위의 함수가 정상적으로 완료되면 action이 실행됨

정상적으로 완료되지 않고 return false 값을 받으면 action은 실행되지 않음


submit 버튼을 눌러도 onsubmit="return false;"로 설정되었다면 action이 일어나지 않음

	<button type="submit" class="btn btn-default" id="btnLogin"></button>
키패드로 enter, submit 가능

<input type="button"> 이거나 onClick으로 submit을 처리하면 키패드로 submit 불가
