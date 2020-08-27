https://start0.tistory.com/223

select option 구별할 때. value는 각기 다르지만 그 값들의 공통 사항을 위해.

    <option value='p93' data-val='ON'>p93</option>

value는 다르지만 data-val=""로 그룹화 시킨다.

    var find = $(this).find("option:selected").data("val");
