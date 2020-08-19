    <script>
          $("#aa").on("change", function(){
            if($("option:selected").attr("data-val") == "a"){
              alert("현재 사용하실 수 없습니다.");
              $("option:selected").prop("selected", false);
            }
          });
    </script>

select option click-change event에서
attr로 가져온 data-val 이 특정 value 값일 때 change return false 하기
근데 return false 안먹음

사용

    $("option:selected").prop("selected", false);
    
이것은 select option 초기 값으로 회귀함. 아예 비워주고 싶음.

사용

    $("select").val([]);

https://www.it-swarm.dev/ko/jquery/jquery%EC%97%90%EC%84%9C-ltselectgt%EB%A5%BC-%EC%84%A0%ED%83%9D-%ED%95%B4%EC%A0%9C%ED%95%98%EB%8A%94-%EA%B0%80%EC%9E%A5-%EC%A2%8B%EC%9D%80-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C/968539257/
