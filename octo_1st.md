#React 컴포넌트
가장 먼저 알아야 하는 것은 React의 컴포넌트입니다. 컴포넌트는 개념적으로 props를 input으로 하고 UI가 어떻게 보여야 하는지 정의하는 React Element를 output으로 하는 함수입니다. 따라서 합성을 이용하여 “UI를 재사용할 수 있고 독립적인 단위로 쪼개어 생각”할 수 있게 합니다. 그래서 컴포넌트는 React.Component를 상속받아 정의하지만 컴포넌트 간에는 상속보다는 합성을 사용하길 권장합니다.


##React 컴포넌트의 props와 state
컴포넌트는 두 가지 인스턴스 속성(property) props와 state를 가지고 있습니다. props는 컴포넌트의 mounting, updating 프로세스 시점에 값이 할당될 뿐 컴포넌트 내부에서 값을 변경할 수 없습니다. 상황에 따라 변경되어야 하는 값들은 state를 이용해야합니다.


컴포넌트 간에는 무조건 props를 통해서만 데이터를 주고받고 props는 컴포넌트 내부에서 변경되지 않습니다.


###React 컴포넌트의 setState() API
컴포넌트는 setState()(이하 ‘setState’)라는 API가 존재합니다. 이름 그대로 컴포넌트의 state를 변경할 때 사용하는 API입니다. 그냥 state를 직접 변경할 수도 있을 텐데 왜 굳이 API를 통해서 변경해야 할까요? 자바스크립트의 비교 연산자는 피연산자의 값이 아닌 reference 값을 기준으로 참/거짓을 리턴하기 때문입니다.


만약 state의 값을 직접 변경할 경우에는 해당 오브젝트의 reference 값이 변하지 않아 컴포넌트는 state가 변경되지 않았다고 볼 수밖에 없습니다. 그러므로 화면이 갱신되지 않는 것이지요. 따라서 React는 setState를 이용해 기존 state와 머지하여 state의 변경 가능성을 명시적으로 알려줍니다. 머지를 통해 새로 생성된 state의 reference 값은 기존과 다르므로 컴포넌트에서는 shallow compare를 통해 변경되었음을 알 수 있습니다. 물론 reference 변경일 뿐이니 실제 값은 변경되지 않을 수도 있습니다.
한 가지 더 중요한 사실은 setState 호출 즉시 state가 변경되는 것이 아니라 비동기로 동작한다는 점입니다. 상태가 변경된 직후에 필요한 작업이 있다면 setState(nextState, callback)의 callback을 사용해야 합니다.
따라서 아래는 보장되지 않습니다.

	1. setState 호출 직후에 state가 즉시 갱신된다.
	2. 한 컨텍스트 내에서의 setState 호출 수와 컴포넌트 업데이트 수는 같다.
	
하지만 다음은 보장됩니다.

	1. setState 실행 순서
	2. setState callback의 실행 순서
	3. state 변화가 클릭 등의 event 실행 전에 컴포넌트에 반영된다.



###Route 컴포넌트
<Route> 컴포넌트는 현재 주소창의 경로와 매치될 경우 보여줄 컴포넌트를 지정하는데 사용됩니다.
path prop을 통해서 매치시킬 경로를 지정하고 component prop을 통해서 매치되었을 때 보여줄 컴포넌트를 할당합니다.
```jsx
	<Route path="/about" component={About} />
```
예를 들어, 위의 코드는 현재 주소창의 경로가 /about일 경우 About라는 컴포넌트를 보여줍니다.
일반적으로 현재 주소창의 URL 경로에 따라 특정 컨텐트를 보여주거나 숨기기 위해서 사용될 수 있습니다.
