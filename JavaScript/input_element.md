### html에서 input 태그의 값을 가져오는 방법
#### jQuery로 input 텍스트 박스 값 가져오기, 초기화(요소의 삭제)


      <input type="text" name="example" id="ex" class="ex_class" value="test">

- id로 접근해서 가져오기

      var value=$("#ex").val();

- name으로 접근해서 가져오기

      var value=$("input[name=example]").val();

- class로 접근해서 가져오기

      var value=$(".ex_class").val();

- 요소의 삭제

      .remove()
      .detach()
      .empty()
      .unwrap()

- input 태그 박스의 값을 초기화 하려면

      $("#ex").val('');
      $("#ex").val('Default Value'); //지정된 값으로 초기화

ref http://www.devkuma.com/books/pages/385

