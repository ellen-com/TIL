# React Hooks

## Hooks 필요한 이유
React에 Hook이 도입된 이유에 관하여 React 페이지에서는 이렇게 말하고 있습니다.
* 컴포넌트 사이에서 상태와 관련된 로직을 재사용하기 어렵습니다.
* React는 컴포넌트에 재사용 가능한 행동을 붙이는 방법을 제공하지 않습니다.
* Class가 코드의 재사용성과 코드 구성을 좀 더 어렵게 만들 뿐만 아니라, React를 배우는데 큰 진입장벽이라는 것을 알게 되었습니다. Javascript에서 어떻게 this가 작동하는지 알아야만 했고, 대부분의 다른 언어와는 다르게 작동합니다.

라고는 하는데 Hook이 도입되기 전 React를 해본적도 없고, 아는 게 너무 없는 신입 개발자이기에 그렇구만.. 하고 넘어갑니다

## 그래서 Hook이란?
Hook은 특별한 함수입니다.
대표적으로 useState는 state를 함수 컴포넌트 안에서 사용할 수 있게 해줍니다.
간단하게 바뀌는 정보를 실시간으로 업데이트 할 때 사용하면 좋은 것 같습니다.
클래스를 사용해서 값의 변화를 반영하는 것보다 useState를 사용하는 것이 코드 길이도 줄이고 직관적이라고 하네요~.~

## 대표적인 React의 useState 어떻게 사용하나요!?
```javascript
import React, { useState } from 'react';
function Example() {
    // 새로운 state 변수 count를 선언
  const [count, setCount] = useState(0);

}
```
### useState 호출로 무엇을 할 수 있나요? 
 - “state 변수”를 선언할 수 있습니다.
일반적으로 일반 변수는 함수가 끝날 때 사라지지만, state 변수는 React에 의해 사라지지 않습니다.

### useState의 인자로 무엇을 넘겨주어야 하나요?
 - useState()Hook의 인자로 넘겨주는 값은 state의 초기 값입니다.
함수 컴포넌트의 state는 클래스와 달리 객체일 필요는 없고, 숫자 타입과 문자 타입을 가질 수 있습니다.

### useState는 무엇을 반환할까요?
- state 변수, 해당 변수를 갱신할 수 있는 함수 이 두 가지 쌍을 반환합니다.

### React 컴포넌트의 setState() API
컴포넌트는 setState()(이하 ‘setState’)라는 API가 존재합니다. 이름 그대로 컴포넌트의 state를 변경할 때 사용하는 API입니다. 그냥 state를 직접 변경할 수도 있을 텐데 왜 굳이 API를 통해서 변경해야 할까요? 자바스크립트의 비교 연산자는 피연산자의 값이 아닌 reference 값을 기준으로 참/거짓을 리턴하기 때문입니다.

#### 위의 예시를 정리하자면~
- useState :: Hook을 React에서 가져옵니다.
- count :: state 변수를 선언하고 0으로 초기화합니다.
- React는 해당 변수를 리렌더링할 때 기억하고, 갱신 될 때마다 값을 제공합니다.
- count 변수의 값을 갱신하려면 setCount를 호출하면 됩니다.

#### 왜 대괄호를 사용하나요?
자바스크립트 문법은 “배열 구조 분해”라고 하고, count와 setCount, 총 2개의 값을 만들고 있습니다.
useState를 이용하여 변수를 선언하면 2개의 아이템 쌍이 들어있는 배열로 만들어집니다. 
첫 번째 아이템은 현재 변수를 의미하고, 두 번째 아이템은 해당 변수를 갱신해주는 함수입니다.
배열 구조 분해라는 특별한 방법으로 변수를 선언해주었기 때문에 [0]이나 [1]로 배열에 접근하는 것은 좋지 않을 수 있습니다.


#### 그래서 useState()는요!
useState를 이용하면 함수 컴포넌트 안에서 state를 사용할 수 있습니다.

내일은 EffectHook에 대해서 정리할게요~ 안뇽~!