# MobX store

## Store
Global영역에서 애플리케이션의 State와 비즈니스로직을 가지고 있고 있는 주체를 Store라고 합니다.

State를 Global한 영역에서 관리한다는 말은 즉 State관리 라이브러리 사용의 목적중 한가지 입니다.

Redux에서는 State와 State를 핸들링하는 비즈니스로직을 가지고 있는 Reducer, Action등을 포함하는 의미 이기도 하지만, Mobx에서 Store는 명확히 State와 비즈니스로직을 포함하는 Class를 Store라고 부릅니다.

출처 : 우아한형제들 기술 블로그


## MobX 라이브러리 설치
mobx 라이브러리 설치 패키지는 <b>yarn</b>을 사용합니다. npm아님

```
$ yarn add mobx mobx-react
```

react 안에서 mobx 라이브러리를 사용하기 위해
```javascript
import React, {Component} from 'react';
import {decorate, observable, action, computed} from 'mobx';
import {observer} from 'mobx-react';
```

글로벌하게 사용될 값 (number)와 값의 변화를 주는 함수들 (increase, decrease)
```javascript
import React, { Component} from 'react';
import { decorate, observable, action } from 'mobx';
import { observer } from 'mobx-react';

class Counter extends Component {
  number = 0;
  
  increase = () => {
    this.number++;
  }
  
  decrease = () => {
    this.number--;
  }
  
  render() {
    return (
      <div>
        <h1>{this.number}</h1>
        <button onClick={this.increase}>+1</button>
        <button onClick={this.decrease}>-1</button>
      </div>
    )
  }
}

decorate(Counter ,{
  number: observable,
  increase: action,
  decrease: action
});

export default observer(Counter);
```
decorate : 해당 컴포넌트의 요소에 mobx 개념을 각각 적용할 수 있도록 해주는 함수.

decorate를 사용하지 않으면 아무 의미가 없으므로 꼭 사용해주어야 합니다.

decorate 기능 대신 decorator로 mobx를 사용하면 훨씬 간편하다구요!

헌데 이는 babel 설정이 필요합니다.
```
$ npm run eject
```

그리고, package.json 내의 babel 설정 부분으로 가서, 아래와 같이 수정한다.
```json
{
  {다른 설정들..}: "설정 값들",
  
  "babel": {
    "presets": [
      "react-app"
    ],
    "plugins": [
      [
        "@babel/plugin-proposal-decorators",
        {
          "legacy": true
        }
      ],
      [
        "@babel/plugin-proposal-class-properties",
        {
          "loose": true
        }
      ]
    ]
  }
}
babel 설정을 한 후, 개발 서버를 껐다 켜야 적용이 된다.
```

이렇게 하면
위의 그 길고 긴 코드를 이렇게 줄일 수 있음!
```javascript
import { observable, action } from 'mobx';

export default class CounterStore {
  @observable number = 0;
  
  @action
  increase = () => {
    this.number++;
  }
  
  @action
  decrease = () => {
    this.number--;
  }
}
```

마지막으로 프로젝트에 store 삽입

```javascript
import React, { Component } from 'react';
import { observer, inject } from 'mobx-react';

@inject('counter')
@observer
class Counter extends Component {
  render() {
    const { counter } = this.props;
    return (
      <div>
        <h1>{counter.number}</h1>
        <button onClick={counter.increase}>+1</button>
        <button onClick={counter.decrease}>-1</button>
      </div>
    );
  }
}

export default Counter;
```

출처 : https://helloinyong.tistory.com/175?category=832497

제가 이 개념을 응용해야하는데 자꾸 기억이 안 나서 기억하려고 적어두는 거에요...
혹시나 위의 글을 삭제하실까봐 ㅜ^ㅜ