### Grave Accent

- 키보드 숫자 1 옆, 쿼티 자판에서 Tab키 위에 있는 `` 기호 Grave accent(발음 구별 기호의 하나)<br>
- `` 문자는 Grave Accent, Backtick, Backquote 등으로 불린다.<br>
- JavaScript에서 Template Literal로 사용된다.<br>
- 마크다운 문법에서 사용하면 코드를 강조한다.


---

### Template Literal

      var number2 = [1, 400, 12, 34, 5];
      var j = 0;
      var total = 0;
      while(j < number2.length){
       total = total + number[j];
       j=j+1;
      }
    
위 결과를 console.log로 찍을 때

- Grave accent 적용 X

      console.log('total :' + total);

- Grave Accent 적용한 __문자열 Template Literal__

      console.log(`total : ${total}`);
    
  - 위의 두 코드의 결과물은 같다. 표현의 차이.
  - 문자열과 변수의 값을 같이 출력할 때, 보통 2번처럼 코딩한다.
  - 문자열 내부에 표현식${}을 쓸 수 있다.
  - 줄바꿈 기호 \n 없이도 줄바꿈 할 수 있다.   
      
ref https://flik.tistory.com/53
    
