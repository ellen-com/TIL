# MobX

## Observable State
전에는 개념만 정리했는데 이번엔 어떻게 사용하는 지 알아봅시다.
왜냐면 제가 이걸 응용해야 할 거 같거든요

제가 일단은 한 컴포넌트에 모든 기능을 때려 넣었는데,
SRP 원칙대로 하나의 클래스에 하나의 책임만 지도록 분리하려고 합니다.

하지만 React는 다른 컴포넌트들의 서로 바꿀 수 없기에...
MobX를 사용하려고 합니다.


```javascript
import { observable } from 'mobx';

//Observable State 만들긔~!
const calculator = observable({
  a: 1,
  b: 2
});
```

Observable State를 사용하면 MobX가 이 객체를 관찰하여 <b>변화를 추적</b>합니다.


## reaction

```javascript
import { reaction } from 'mobx';

//calculator의 a 값이 바뀔 때마다 작업하기
reaction(
  () => calculator.a,
  (value, reaction) => {
    console.log(`reaction :: a 값 = ${value}`);
  }
);
```


## computed
```javascript
// computed로 sum 값 캐싱! sum 값이 바뀔 때 마다 실행
const sum = computed(() => {
  console.log('계산중이예요!');
  return calculator.a + calculator.b;
});
```

# ES6을 사용하면 더 깔끔하게 할 수 있대요
근데 저는 클래스를 사용하지 않고 있어서...
이건 더 공부하고 올려야겠어요

참고 : https://velog.io/@velopert/begin-mobx