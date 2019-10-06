# React에서 많이 나오는데 나는 모르는 용어 정리

## React
일단 React가 뭔가요? 했을 때 대답은 할 수 있어야하지 않을까...! 하지만 난 못 했지..ㅎ

일단 React란 <b> 프론트엔드 라이브러리 </b>로, 프론트엔드를 동적으로 관리하기 위한 라이브러리입니다.
React의 핵심 개념 == Component (뒤에 나옴)

### Virtual DOM
일단 <b>DOM</b> 이란 Document Object Model의 약자로, 객체를 통해 구조화된 문서를 표현하는 방법입니다.
+ DOM은 트리형태임!

#### 그래서 Virtual DOM이 뭐냐고!
 -> DOM의 상태를 메모리에 저장하고 변경된 내용만 반영 하는 기능
 
DOM에 업데이트 하는 절차
```
React에서 데이터가 변하여 브라우저 상의 실제 DOM에 업데이트 하는 과정은 3가지 절차를 밟습니다.

1.  데이터가 업데이트 되면, 전체 UI를 Virtual DOM에 리렌더링 합니다.

2.  이전 Virtual DOM에 있던 내용과 현재의 내용을 비교합니다.

3. 바뀐 부분만 실제 DOM에 적용이 됩니다.
```

## Router
 :: 사용자가 요청한 URL에 따라서 결과물을 렌더링해줍니다. 
 
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import PathRouting from './Routing';

ReactDOM.render(
  <PathRouting />,
  document.getElementById('root'),
);

```
PathRouting
```javascript
import React from 'react';
import { Route, Switch, } from 'react-router-dom';
const PathRouting = () => (
    <Switch>
        <Route exact name="home" path="/" component={Summary} />
        <Route exact name="First" path="/first" component={First} />
    </Switch>
);
```
오늘은 여기까지~