# MobX state tree

* store(mst에서 상태를 저장해 놓은 object)에서 observable property들을 제공
* React.component에서 <b>observer</b>를 해주면 값 변경시 다시 page rendering이 이루어짐
   -> 정확히 얘기하자면 해당 property를 사용하는 곳이 새로 실행된다

## store
* types.model로 선언
* object임 근데 JSON object와 달라서 .toJS()를 이용해서 출력해야 console.log에 잘 찍힘

## action
action으로 값을 받아서 실행했을 때 observer로 선언한 곳에서 사용하더라도 재실행 안 될 수 있으므로 가능하면 view를 사용하래요

// view도 공부하기

```
types.model의 값을 읽는건 어디서든 가능하지만 변경하는 것은 해당 model 내의 action에서만 가능하다. 이건 부모 tree든 자식 tree든 마찬가지다. 그래서 외부에서 변경해야하는 property에 대해서는 action에 setter를 생성해야 한다.
```

참고 : https://devstarsj.github.io/development/2019/05/19/mobx-state-tree.usage/

내일 계속..