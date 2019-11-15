체크박스는 목록에서 하나 혹은 몇 개의 옵션을 선택, 라디오는 여러 개 중 하나의 옵션을 선택한다.<br>
체크박스는 복수로 선택이 가능하며, 자동으로 그 취소는 되지 않는다.<br>
라디오버튼처럼 단 한 개만 선택할 수 있는 자바스크립트 예제.

    <label for="exampleInputEmail1">분류</label>
            <div class="checkbox">
              <input type="checkbox" name="aa" value="korea" onclick="doCheck(this);">국내영화
            </div>
            <div class="checkbox">		    
              <input type="checkbox" name="aa" value="abroad" onclick="doCheck(this);">국외영화
            </div>
            <div class="checkbox">		    
              <input type="checkbox" name="aa" value="etcetera" onclick="doCheck(this);">기타영상
            </div>

'this'를 넘겨 클릭된 객체의 값을  전달하여, 같은 name의 값을 가져온 것과 비교하면서<br>
클릭한 객체와 일치하지 않으면 체크를 해제한다.

    <script>
      function doCheck(chk){
        var obj=document.getElementsByName("aa");
        for(var i=0; i<obj.length; i++){
          if(obj[i] != chk){
            obj[i].checked=false;
          }
        }
      }	
    </script>
