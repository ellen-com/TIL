#ES6
ES6는 ECMAScript6라고 불리며, 자바스크립트 언어의 표준입니다.

## 화살표 함수
```javascript
//매개변수 지정 방법
() => {} //매개변수X
x => {} // 매개변수가 하나일 경우, 소괄호 생략 가능
(x, y) => {}

// 함수 몸체 지정 방법
x => { return x * x }
x => x * x  // 함수 몸체가 한줄의 구문이라면 중괄호를 생략할 수 있으며 암묵적으로 return된다. 위 표현과 동일

() => { return { a: 1 }; }
() => ({ a: 1 })  // 위 표현과 동일. 객체 반환시 소괄호를 사용한다.

() => { //여러줄일 경우
  const x = 10;
  return x * x;
};
```
화살표 함수의 호출
```javascript
const pow = x => x * x;
// const pow = 매개변수 x, x*x값을 반환
```

```javascript
// ES6
const arr = [1, 2, 3];
const pow = arr.map(x => x * x);

console.log(pow); // [ 1, 4, 9 ]
```

화살표 함수에서의 this는 상위 스코프의 this를 가리킨다.
```javascript
window.x = 1;
const normal = function () { return this.x; };
const arrow = () => this.x;

console.log(normal.call({ x: 10 })); // 10
console.log(arrow.call({ x: 10 }));  // 1
```

[참고] https://poiemaweb.com/es6-arrow-function

## 변수
사용할 수 있는 변수로는 const, let, var가 있지만, var는 사용하지 않습니다.
* const : 값이 지정되면 나중에 바꿀 수 없습니다.
* let : 값이 지정되어도 나중에 값을 바꿀 수 있습니다.

## Modules
export, import를 이용해 function이나 변수를 다른 곳에서 사용할 수 있습니다.

```javascript
// exportEx.js
export const exportFunc = (x) => {return x*x}

//importEx.js
import { exportFunc } from "exportEx"
console.log(exportFunc(3)) //9
```

## Promise
이건 제가 써본 적 없어서 아직은 잘 모르겠습니다.

비동기 프로세싱을 위해 사용됩니다. (Asynchronously)
가독성이 좋으며 중첩된 콜백의 단점을 완화합니다.
(Callback Hell이라는 Callback 함수가 다시 Callback을 호출하고 또다시 Callback을 호출하는 코드를 읽기도 관리하기도 힘들어지는 것은 완화할 수 있습니다.)

Promise의 세가지 상태

대기중(pending)
이행됨(fulfilled)
거부됨(rejected)
라고하네요. 출처 : http://woowabros.github.io/experience/2017/12/01/es6-experience.html