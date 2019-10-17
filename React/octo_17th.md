# useContext

useContext 전에는 이해를 못 했었는데
지금은 써야해서 이해를 해야만 합니다....
다시 보니까 또 알 거 같더라구요

useContext
```javascript
const value = useContext(MyContext);
```
context 객체(React.createContext에서 반환된 값)을 받아 그 context의 현재 값을 반환합니다.
context의 현재 값은 트리 안에서 이 Hook을 호출하는 컴포넌트에 가장 가까이에 있는 <MyContext.Provider>의 value prop에 의해 결정됩니다.

컴포넌트에서 가장 가까운 <MyContext.Provider>가 갱신되면 이 Hook은 그 MyContext provider에게 전달된 가장 최신의 context value를 사용하여 렌더러를 트리거 합니다.

useContext로 전달한 인자는 context 객체 그 자체이어야 합니다.

그래서 또 Context의 Provider는 무엇인고... 하냐면

## Context.Provider
```javascript
<MyContext.Provider value={/* 어떤 값 */}>
```
Context 오브젝트에 포함된 React 컴포넌트인 Provider는 context를 구독하는 컴포넌트들에게 context의 변화를 알리는 역할을 합니다.

Provider 는 value prop를 받아서 이 값을 하위에 있는 컴포넌트에게 전달합니다.

Provider 하위에서 context를 구독하는 모든 컴포넌트는 Provider의 value prop가 바뀔 때마다 다시 렌더링 됩니다.

## Context.Consumer
```javascript
<MyContext.Consumer>
  {value => /* context 값을 이용한 렌더링 */}
</MyContext.Consumer>
```
context 변화를 구독하는 React 컴포넌트입니다.
함수 컴포넌트안에서 context를 읽기 위해서 쓸 수 있습니다.

Context.Consumer의 자식은 함수여야합니다. 이 함수는 context의 현재값을 받고 React 노드를 반환합니다. 이 함수가 받는 value 매개변수 값은 해당 context의 Provider 중 상위 트리에서 가장 가까운 Provider의 value prop과 동일합니다. 상위에 Provider가 없다면 value 매개변수 값은 createContext()에 보냈던 defaultValue와 동일할 것입니다.


출처. reacts.org

아니 근데 개념 보면 알겠는데 또 응용하려니 힘들더라구요 에혓