HashMap NULL CHECK

    for(Object val : map.values()) {
        if (val == "" || "null".equals(val) || val == null) {
          //과세구분 미입력시 과세(N)로 지정
          map.put("taxYn", "N");
          map.put("svcAmt", "");
          map.put("deductionType", "");
          map.put("ordNm", "");
          if("0".equals(assort)) {
          }else if("1".equals(assort)) {
            map.put("amt", "");
            map.put("vat", "");
            map.put("bizRegNo", "");
            map.put("purpose", "");
            map.put("identityGb", "");
            map.put("identity", "");
          }
        } 
      }
      
      
      
values() 값을 뒤진다<br>
keySet() 키값이 필요한 경우<br>
entrySet() 키와 value.


ref https://starblood.tistory.com/entry/Map-HashMap-%EC%88%9C%ED%9A%8C%ED%95%98%EA%B8%B0
      
