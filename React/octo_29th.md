# React Context
큰 규모의 앱에서는 전역 데이터를 관리하는데 좀 더 나은 접근 방식이 필요합니다.
React Context는 전역 데이터를 좀 더 단순하지만 체계적인 방식으로 접근할 수 있도록 도와줍니다.

## Context 생성
React Context는 전역 데이터를 담고 있는 하나의 저장 공간.
전역 데이터를 관리하기 위해서 createContext 함수 사용

```javascript
import { createContext } from "react";
//Example Context에 기본으로 저장할 값 example 전달
const ExampleContext = createContext("example");
```

## Context 저장
컴포넌트 내에서 Provider로 감싸주면, 하위에 있는 모든 컴포넌트들은 React Context에 저장되어 있는 전역 데이터에 접근 가능.

```javascript
render() {
    const { lang } = this.state;
    return (
      <LangContext.Provider value={lang}>
        <Button toggleLang={this.toggleLang} />
        <Title />
        <Message />
      </LangContext.Provider>
    );
  }
```

## useContext로 Context접근
eact Hooks에서 추가된 useContext 함수를 이용하면 좀 더 깔끔하게 Context에 저장되어 있는 전역 데이터에 접근할 수 있습니다.
Button 컴포넌트는 useContext 함수에 LangContext를 넘김으로써 사용자 언어 설정값을 읽습니다.

<b>단, 이 방법은 함수 컴포넌트에서만 사용 가능합니다.</b>

```javascript
import React, { useContext } from "react";
import LangContext from "./LangContext";

function Button({ toggleLang }) {
  const lang = useContext(LangContext);
  return <button onClick={toggleLang}>{lang}</button>;
}
```

출처 : https://www.daleseo.com/react-context/
useContext쓰려는데 진짜 어렵다..