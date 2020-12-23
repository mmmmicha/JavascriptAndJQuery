# Javascript&JQuery

- 개요 : Javascript와 Jqeury의 다양한 예제정리와 개념 정리

## 비교
### == vs ===
- 1=='1' // `true`
- 1==='1' // `false`

- null == undefined // `true`
- null === undefined // `false`
- true == 1 // `true`
- true === 1 // `false`
- true == '1' // `true`
- true === '1' // `false`

- 0 === -0 // `true`
- NaN === NaN // `false`

## 조건문
- 0 은 `false`, 0 이 아닌 값은 `true`
- 이외의 `false` : '', undefined, 값이 할당되지 않은 변수(ex. var a), null, NaN

## 배열
### 내장 함수
- Array.push : 배열끝에 원소 추가
- Array.concat : 복수의 원소를 배열에 추가
- Array.unshift : 배열의 시작점에 원소를 추가
- Array.splice : 첫번째 인자에 해당하는 원소부터 두번째 인자에 해당하는 원소의 숫자만큼의 값을 배열로부터 제거한 후에 리턴
- Array.shift : 배열의 첫번째 원소를 제거
- Array.pop : 배열 끝점의 원소를 배열에서 제거
- Array.sort : 정렬
- Array.reverse : 역정렬

## 객체
### 객체배열
```
for(key in Object) {
  document.write("key : " + key + " value : " + Object[key]);
}
```

## 전역변수를 활용하는 방법
- 전역변수는 웬만하면 사용하지 않는 편이 좋다.
- 불가피하게 사용하는 경우엔 '하나의 객체' 를 전역변수로 만들고 객체의 속성으로 변수를 관리하는 방법을 사용한다.

## 클로저
- 내부함수가 외부함수의 맥락에 접근할 수 있는 것
- 함수 내 함수
- 고급 코딩에 사용된다고 함

## arguments
- 함수의 파라미터로 넘어온 값들의 유사배열(배열은 아니고 arguments 객체의 인스턴스이다.)
- .length 를 사용할 수 있음
 
## apply, call 함수
- Function 자체도 객체이기 때문에 프로퍼티로 위 함수들을 지니고 있다.

예제1)
```
function sum(arg1, arg2){
    return arg1+arg2;
}
alert(sum.apply(null, [1,2]))
```

예제2)
```
o1 = {val1:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}
function sum(){
    var _sum = 0;
    for(name in this){
        _sum += this[name];
    }
    return _sum;
}
alert(sum.apply(o1)) // 6
alert(sum.apply(o2)) // 185
```

## 객체
- 자바스크립트에서의 객체는 2가지 방법으로 나뉜다.
1. {} 2. function
- 클래스가 없다.
- function 이 그냥 생성자함수의 역할을 한다.
- new function 으로 만들어진 객체는 이 생성자 내부에 선언되어 있는 속성들을 그대로 갖게 된다.
- new 방식으로 객체가 만들어지게 되면 자연스럽게 proto 객체도 갖게 된다.
- new 방식으로 만들어진 객체는 기존 함수와 구별하기 위해 네이밍 첫글자를 대문자로 표시한다.
- 생성자함수는 말그대로 생성자함수이다. new 로 객체를 만들어야만 내부 프로퍼티를 다룰 수 있다. 즉, 생성자함수를 선언만해놨다고 해서 그 내부를 control 할 수 없다.

## 전역객체
- window

## this
- new 생성자로 객체 만들면 this 는 그 생성된 객체
- 생성자 선언만 되어있는 경우 this 는 전역객체(window)
- apply, call 로 객체를 넘기면 this 는 그 객체

## 상속 & prototype
- prototype chain 연결로 인해 객체에서 프로퍼티를 찾다 없으면 chain을 다 뒤지게 된다.

```
function Ultra(){}
Ultra.prototype.ultraProp = true;
 
function Super(){}
Super.prototype = new Ultra();
 
function Sub(){}
Sub.prototype = new Super();
 
var o = new Sub();
console.log(o.ultraProp);
```

## 정규식
- 한글이 아닌 것
`var kor = /([^가-힣ㄱ-ㅎㅏ-ㅣ\x20])/i;`
- 영어가 아닌 것
`var eng = /^[A-za-z]/g`
- 숫자만!
`var num = /^[0-9]*$/;`

- 같이쓰는 함수
  - val2.search(val1) : val2 내 val1이 있는 index를 반환한다. 없을 경우 -1 을 반환한다.
  - val2.test(val1) : val2 내 val1이 있는 index를 반환한다. true, false
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
      
