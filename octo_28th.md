# MobX store

## Store
Global�������� ���ø����̼��� State�� ����Ͻ������� ������ �ְ� �ִ� ��ü�� Store��� �մϴ�.

State�� Global�� �������� �����Ѵٴ� ���� �� State���� ���̺귯�� ����� ������ �Ѱ��� �Դϴ�.

Redux������ State�� State�� �ڵ鸵�ϴ� ����Ͻ������� ������ �ִ� Reducer, Action���� �����ϴ� �ǹ� �̱⵵ ������, Mobx���� Store�� ��Ȯ�� State�� ����Ͻ������� �����ϴ� Class�� Store��� �θ��ϴ�.

��ó : ����������� ��� ��α�


## MobX ���̺귯�� ��ġ
mobx ���̺귯�� ��ġ ��Ű���� <b>yarn</b>�� ����մϴ�. npm�ƴ�

```
$ yarn add mobx mobx-react
```

react �ȿ��� mobx ���̺귯���� ����ϱ� ����
```javascript
import React, {Component} from 'react';
import {decorate, observable, action, computed} from 'mobx';
import {observer} from 'mobx-react';
```

�۷ι��ϰ� ���� �� (number)�� ���� ��ȭ�� �ִ� �Լ��� (increase, decrease)
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
decorate : �ش� ������Ʈ�� ��ҿ� mobx ������ ���� ������ �� �ֵ��� ���ִ� �Լ�.

decorate�� ������� ������ �ƹ� �ǹ̰� �����Ƿ� �� ������־�� �մϴ�.

decorate ��� ��� decorator�� mobx�� ����ϸ� �ξ� �����ϴٱ���!

�嵥 �̴� babel ������ �ʿ��մϴ�.
```
$ npm run eject
```

�׸���, package.json ���� babel ���� �κ����� ����, �Ʒ��� ���� �����Ѵ�.
```json
{
  {�ٸ� ������..}: "���� ����",
  
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
babel ������ �� ��, ���� ������ ���� �Ѿ� ������ �ȴ�.
```

�̷��� �ϸ�
���� �� ��� �� �ڵ带 �̷��� ���� �� ����!
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

���������� ������Ʈ�� store ����

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

��ó : https://helloinyong.tistory.com/175?category=832497

���� �� ������ �����ؾ��ϴµ� �ڲ� ����� �� ���� ����Ϸ��� ����δ� �ſ���...
Ȥ�ó� ���� ���� �����ϽǱ�� ��^��