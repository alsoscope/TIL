달력 위젯 스크립트.

API 문서
https://bootstrap-datepicker.readthedocs.io/en/latest/index.html

input이 2개이기에 datepicker 각각 연동시켜서,<br>
시작일은 종료일보다 클 수 없고 종료일은 시작일보다 적을 수 없도록 한다.<br>
: 시작일 선택 후 종료일은 시작일 이전의 항목을 선택할 수 없게 한다.(disabled)

jquery datepicker가 아닌 bootstrap datepicker

    $('.datepicker').datepicker({
        onClose: function () {
            alert('wow');
        }
    });

__change form ↓__

    $('.datepicker').datepicker().on('hide', function(e) {
        console.log('wow');
    });

Markup endDate 옵션

    <input type="text" class="form-control" data-date-end-date="0d">
    Will disable all dates after today.

endDate 사용은 두 개 input 모두에 적용된다.

- 이벤트

		$('#start').datepicker().on('hide',function(e){
			console.log('www');
		});

		$('#end').datepicker().on('show', function(e){
			console.log('www');
		});

- show : datepicker가 보여지는 순간 호출
- hide : datepicker가 숨겨지는 순간 호출

- changeDate : 사용자가 클릭해서 날짜가 변경되면 호출

- clearDate : clear 버튼 누르면 호출<br>
(clearBtn : 선택한 날짜 값 초기화해주는 버튼이 보여지는 옵션(삭제 버튼), 기본값 false 보이려면 true)

달력 선택시 setStartDate, setEndDate가 설정되도록 한다.

- setStartDate : 

- setEndDate

ref<br>
https://programmer93.tistory.com/5<br>
https://blog.uhoon.co.kr/entry/bootstrap-datepicker-From-To-%EC%9D%B4%EC%A0%84-%EB%82%A0%EC%A7%9C-%EC%9D%B4%ED%9B%84-%EB%82%A0%EC%A7%9C-%EC%84%A0%ED%83%9D-%EB%AA%BB%ED%95%98%EA%B2%8C-%ED%95%98%EA%B8%B0
