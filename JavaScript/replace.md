#### replace 데이터 치환

    var a = $('#a').val().replace(/\n/gi, "");

/n값을 "" 로 바꾸기

바꾸고 싶은 문자열을 // 로 감싸고 뒤에 gi를 붙여서 전체를 바꾼다.


#### input 숫자만 입력하기

    <input type="text" id="a" size=2 maxlength=2 onKeyup="this.value=this.value.replace(/[^0-9]/g, '');" placeholder="DD" class="tabFocus">

    onKeyup="this.value=this.value.replace(/[^0-9]/g, '');"

    function numOnly(obj){
            var a = obj.value;
            obj.value=a.replace(/[^0-9]/gi, "");
    }
