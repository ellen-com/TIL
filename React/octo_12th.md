# React는 어떻게 작동하는 걸까요?
React에서는 어떻게 DOM을 렌더링하고 브라우저 이벤트를 처리할까요?

## Virtual DOM
React는 실제로 DOM을 제어하는 방식이 아니라 중간에 Virtual DOM을 둡니다. 이를사용함으로써, 개발의 편의성과 성능을 개선했다고 하는데 저는... 아직 잘 모르겠어요.
무튼 React의 주요 장점인 Virtual DOM은 어떻게 만들어지고 관리될까요?

### Virtual DOM 렌더링
Virtual DOM은 React의 객체 트리입니다.
개발자는 직접 DOM을 제어하지 않고 Virtual DOM을 제어하고, React에서 적절하게 Virtual DOM을 DOM에 반영하는 작업을 합니다.

일단 JSX문법을 사용한 ReactDOM.render()함수를 호출하면 Virtual DOM을 만들기 시작합니다.

```javascript
ReactDOM.render(
      <App/>,
    document.getElementById('root')
  )
```

이 코드의 JSX문법을 변환하면 다음과 같은 JavaScript코드가 만들어집니다.
```javascript
ReactDOM.render( //render() 함수를 호출할 때
    React.createElement(App) //React.createElement(App)객체를 파라미터로 전달하며
  , document.getElementById('root'));
```
render()함수는 React에서 사용하는 타입의 컴포넌트를 생성합니다.

* ReactCompositeComponent 객체 : DOM이 아닌 컴포넌트를 생성할 때 사용
* ReactDOMComponent 객체 : DOM을 만들 때 생성하는 컴포넌트

render() 함수가 생성한 컴포넌트를 React 컴포넌트에 마운트 하기 위해
ReactReconciler.mountComponent() 메서드를 호출합니다.
이 메서드에서는 위의 두 객체의 mountComponent() 메서드를 호출하며, 이 시점에 주요 작업이 시작됩니다.

주요 작업은... 생략!

App 컴포넌트가 생성되면 <div> 엘리먼트를 생성합니다.
<div> 엘리먼트와 같은 실제 DOM과 함께 ReactDOMComopnent 객체가 생성되며 주요 작업은 다음과 같습니다.

* 실제 DOM을 생성
* style 속성과 attr 속성 추가
* 배치 처리 작업에 사용자 이벤트 등록
등등...


+render() 함수를 호출하는 방법은 store가 변경됐을 때 Virtual DOM을 갱신하는 방법입니다.

이 뒤는 어려워서... 다음에 계속...
참고 https://d2.naver.com/helloworld/9297403