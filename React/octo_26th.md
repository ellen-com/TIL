# JSX

리액트에서는 JSX라는 언어를 사용합니다.
JSX가 뭔지 간단히 정리할까합니다.

오늘은 딱히 공부한 것도 없어서....

```javascript
const element = <h1>Hello, world!</h1>;
```
html을 닮은 이 문법은 JSX로, 자바스크립트의 문법 확장입니다.

JSX는 React 요소를 만들고, 이 요소는 DOM에서 렌더링 됩니다.

## JSX 속성
속성에 중괄호를 이용해 자바스크립트 표현식을 포함시킬 수 있습니다.
```javascript
const element = <img src={user.avatarUrl}></img>;
```
JSX는 HTML보다는 자바스크립트에 가깝기 때문에, React DOM은 HTML 속성 이름 대신 camelCase 속성 이름 컨벤션을 사용합니다.

## JSX 객체 표현

Babel은 JSX를 React.createElement() 호출로 컴파일하기 때문에, 두 예제는 동일합니다.
```javascript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```
```javascript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```