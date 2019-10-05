# React Hooks - useContext

## context? 뭐야 언제 쓰면 되는거야
context를 이용하면 단계마다 일일이 props를 넘겨주지 않고도 컴포넌트 트리 전체에 데이터를 제공할 수 있습니다.
그러므로 context는 React 컴포넌트 트리 안에서 전역적으로 데이터를 공유하고 싶을 때 사용하면 좋습니다.  
ex) 
```javascript
// light를 기본값으로 하는 테마 context를 만들어 봅시다.
const ThemeContext = React.createContext('light');

class App extends React.Component {
  render() {
    // Provider를 이용해 하위 트리에 테마 값을 보내줍니다.
    return (
      <ThemeContext.Provider value="dark">
        <Toolbar />
      </ThemeContext.Provider>
    );
  }
}

class ThemedButton extends React.Component {
  // 현재 선택된 테마 값을 읽기 위해 contextType을 지정합니다.
  static contextType = ThemeContext;
  // React는 가장 가까이 있는 테마 Provider를 찾아 그 값을 사용할 것입니다.
  render() {
    // 이 예시에서 현재 선택된 테마는 dark입니다.
    return <Button theme={this.context} />;
  }
}
```

## useContext 어떻게 사용하면 될까요?
```javascript
import React, { createContext, useContext } from 'react';

//일단 컨텍스트를 생성해줍니다.
const ThemeContext = createContext('red');
const ContextExample = () => {
  const theme = useContext(ThemeContext);
  const style = {
    background: theme
  };
  return <div style={style} />;
};

export default ContextExample;
```

```javascript
import React from 'react';
import ContextExample from './ContextExample';

const App = () => {
  return <ContextExample />;
};

export default App;
```

// 사실 context, useContext 다 맘에 와닿진 않네요... 언젠간 다 이해됐으면 좋겠습니다