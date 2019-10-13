# React Router란

React는 SPA(Single Page Application)을 개발할 때 사용하는데,
이때 흔히 겪는 어려움 중 하나가 웹페이지 라우팅이라고 하더라구요...?

react-router란 클라이언트 사이드에서 주소값의 변경에 따라 페이지 혹은 컴포넌트의 변화를 제공하기 위한 라이브러리입니다.


기본적으로 SPA는 index.html 파일에 div 엘리먼트만 하나 두고, 자바스크립트로 모든 부분을 동적으로 랜더링하는 구조를 취합니다.
그리고 바뀐 부분만 동적으로 갱신해주져.

## 그래서 React Router를 사용하기 위해서?

React Router를 설치해야겠져...
설치 방법
```javascript
$ npm i react-router-dom
```

React Router를 이해하는데 핵심이 되는 3가지 컴포넌트를 봅시다

## Link Component
HTML의 <a> 태그와 유사한 기능을 하는 컴포넌트라고 생각하세여

<a>태그는 href 속성을 통해 이동할 경로를 지정하지만,
<Link> 컴포넌트는 to prop를 통해 이동할 경로를 지정합니다.

```javascript
<Link to="/about">About</Link>
```
위의 코드는 브라우저에서 클릭이 가능한 About으로 랜더링되고, About를 클릭하면 주소창의 경로가 <도메인 네임>/about으로 갱신됩니다.
일반적으로 화면 상단이나 좌측에 위치한 네비게이션 바를 구현할 때 주로 사용하게되는 컴포넌트입니다.

## Route Component
<Route> 컴포넌트는 현재 주소창의 경로와 매치될 경우 보여줄 컴포넌트를 지정하는데 사용됩니다.
path prop을 통해서 매치시킬 경로를 지정하고 component prop을 통해서 매치되었을 때 보여줄 컴포넌트를 할당합니다.
```javascript
<Route path="/about" component={About} />
```
위의 코드는 현재 주소창의 경로가 /about일 경우 About라는 컴포넌트를 보여줍니다.
일반적으로 현재 주소창의 URL 경로에 따라 특정 컨텐트를 보여주거나 숨기기 위해서 사용될 수 있습니다.


## Router Component
<Router> 컴포넌트는 위에 나온 <Route>와 <Link> 컴포넌트가 함께 유기적으로 동작하도록 묶어주는데 사용합니다.
다시 말해, <Route>와 <Link> 컴포넌트는 DOM 트리 상에서 항상 <Router>를 공통 상위 컴포넌트로 가져야합니다.

참고 : https://www.daleseo.com/react-router-basic/
기억하려고 적어두는 것이 똑같아져 부렀네요...