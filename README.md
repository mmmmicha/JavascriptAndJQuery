# Javascript&JQuery

- 개요 : Javascript와 Jqeury의 다양한 예제정리와 개념 정리

- 정리
  - 정규식
    - 한글이 아닌 것
      > var kor = /([^가-힣ㄱ-ㅎㅏ-ㅣ\x20])/i;
    - 영어가 아닌 것
      > var eng = /^[A-za-z]/g
    - 숫자만!
      > var num = /^[0-9]*$/;
      
    - 같이쓰는 함수
      > val2.search(val1) : val2 내 val1이 있는 index를 반환한다. 없을 경우 -1 을 반환한다.<br>
      > val2.test(val1) : val2 내 val1이 있는 index를 반환한다. true, false<br>
      > val2.replace(val1, val3) : val2 내 val1을 val3로 변환한다. 자매품 replaceAll()
      
