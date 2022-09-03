## 1. 코어 자바스크립트

### b. 자바스크립트 기본

JS 기본 문법

[공부 대상](https://ko.javascript.info/first-steps)

<details>
  <summary>화살표 함수 기본</summary>
  arrow function은 함수 표현식보다 단순하고 간결하다.

```js
let sum = (a, b) => a+b  // 인자 a, b를 받아 a+b 반환

let sum = function(a,b){ // 동일한 기능
  return a+b
}

let sum = (a, b) => {    // 동일한 기능
  let result = a+b
  return result
}

sum(1,2) // 3

----

// 인수가 하나면 괄호 생략 가능
let double = n => n*2
double(3) // 6

// 인수가 없으면 괄호 비우기 가능, 생략 불가능
let hi = () => console.log("hello!")

----
// 문제 : 화살표 함수로 변경하기
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "동의하십니까?",
  function() { alert("동의하셨습니다."); },
  function() { alert("취소 버튼을 누르셨습니다."); }

----
// 풀이
let ask = (question, yes, no) => 
  confirm(question) ? yes() : no()

ask("동의하십니까?", () => alert("동의완료!"), () => alert("취소!"))
```
  </details>

> 알게된 내용 정리
>
> 화살표 함수 사용법에 익숙해져야겠다.