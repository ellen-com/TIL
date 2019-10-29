# React Context
ū �Ը��� �ۿ����� ���� �����͸� �����ϴµ� �� �� ���� ���� ����� �ʿ��մϴ�.
React Context�� ���� �����͸� �� �� �ܼ������� ü������ ������� ������ �� �ֵ��� �����ݴϴ�.

## Context ����
React Context�� ���� �����͸� ��� �ִ� �ϳ��� ���� ����.
���� �����͸� �����ϱ� ���ؼ� createContext �Լ� ���

```javascript
import { createContext } from "react";
//Example Context�� �⺻���� ������ �� example ����
const ExampleContext = createContext("example");
```

## Context ����
������Ʈ ������ Provider�� �����ָ�, ������ �ִ� ��� ������Ʈ���� React Context�� ����Ǿ� �ִ� ���� �����Ϳ� ���� ����.

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

## useContext�� Context����
eact Hooks���� �߰��� useContext �Լ��� �̿��ϸ� �� �� ����ϰ� Context�� ����Ǿ� �ִ� ���� �����Ϳ� ������ �� �ֽ��ϴ�.
Button ������Ʈ�� useContext �Լ��� LangContext�� �ѱ����ν� ����� ��� �������� �н��ϴ�.

<b>��, �� ����� �Լ� ������Ʈ������ ��� �����մϴ�.</b>

```javascript
import React, { useContext } from "react";
import LangContext from "./LangContext";

function Button({ toggleLang }) {
  const lang = useContext(LangContext);
  return <button onClick={toggleLang}>{lang}</button>;
}
```

��ó : https://www.daleseo.com/react-context/
useContext�����µ� ��¥ ��ƴ�..