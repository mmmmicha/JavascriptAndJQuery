# Javascript&JQuery

- 개요 : Javascript와 Jqeury의 다양한 예제정리와 개념 정리

## 정규식
- 한글이 아닌 것
  - var kor = /([^가-힣ㄱ-ㅎㅏ-ㅣ\x20])/i;
- 영어가 아닌 것
  - var eng = /^[A-za-z]/g
- 숫자만!
  - var num = /^[0-9]*$/;

- 같이쓰는 함수
  - val2.search(val1) : val2 내 val1이 있는 index를 반환한다. 없을 경우 -1 을 반환한다.<br>
  - val2.test(val1) : val2 내 val1이 있는 index를 반환한다. true, false<br>
  - val2.replace(val1, val3) : val2 내 val1을 val3로 변환한다. 자매품 replaceAll()

## 많이 사용하는 함수

### 시간
  - new Date() : 년/월/일에 대한 API를 갖고 있는 객체.
    - (new Date()).getFullYear() : 로컬 시간의 연도를 반환
    - (new Date()).getMonth() : 로컬 시간의 (월값-1)을 반환 
    - (new Date()).getDate() : 로컬 시간의 일 값을 반환
    - (new Date()).getDay() : 로컬 시간의 주 기준 일값을 반환
      - ex) 일요일 : 0, 월요일 : 1 ...
    - 현재 시간 : (new Date()).getFullYear() + ((new Date()).getMonth()+1+"").padStart(2,"0") + (((new Date()).getDate()+"").padStart(2,"0")
    
 ### PAD
  - String.prototype.padStart() : 현재 문자열의 시작을 다른 문자열로 채워, 주어진 길이를 만족하는 새로운 문자열을 반환.
    - ex)
    ``` 
      const str1 = '5';
      
      str1.padStart(2, '0');
      // output : 05
      
    ```
  - String.prototype.padEnd() : 현재 문자열에 다른 문자열을 채워, 주어진 길이를 만족하는 새로운 문자열을 반환.
    - ex)
    ```
      const str1 = 'abcdefg';
      
      str1.padEnd(10, 'hij');
      // output : abcdefghij
    
    ```
      
