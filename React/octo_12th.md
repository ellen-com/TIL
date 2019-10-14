# React�� ��� �۵��ϴ� �ɱ��?
React������ ��� DOM�� �������ϰ� ������ �̺�Ʈ�� ó���ұ��?

## Virtual DOM
React�� ������ DOM�� �����ϴ� ����� �ƴ϶� �߰��� Virtual DOM�� �Ӵϴ�. �̸���������ν�, ������ ���Ǽ��� ������ �����ߴٰ� �ϴµ� ����... ���� �� �𸣰ھ��.
��ư React�� �ֿ� ������ Virtual DOM�� ��� ��������� �����ɱ��?

### Virtual DOM ������
Virtual DOM�� React�� ��ü Ʈ���Դϴ�.
�����ڴ� ���� DOM�� �������� �ʰ� Virtual DOM�� �����ϰ�, React���� �����ϰ� Virtual DOM�� DOM�� �ݿ��ϴ� �۾��� �մϴ�.

�ϴ� JSX������ ����� ReactDOM.render()�Լ��� ȣ���ϸ� Virtual DOM�� ����� �����մϴ�.

```javascript
ReactDOM.render(
      <App/>,
    document.getElementById('root')
  )
```

�� �ڵ��� JSX������ ��ȯ�ϸ� ������ ���� JavaScript�ڵ尡 ��������ϴ�.
```javascript
ReactDOM.render( //render() �Լ��� ȣ���� ��
    React.createElement(App) //React.createElement(App)��ü�� �Ķ���ͷ� �����ϸ�
  , document.getElementById('root'));
```
render()�Լ��� React���� ����ϴ� Ÿ���� ������Ʈ�� �����մϴ�.

* ReactCompositeComponent ��ü : DOM�� �ƴ� ������Ʈ�� ������ �� ���
* ReactDOMComponent ��ü : DOM�� ���� �� �����ϴ� ������Ʈ

render() �Լ��� ������ ������Ʈ�� React ������Ʈ�� ����Ʈ �ϱ� ����
ReactReconciler.mountComponent() �޼��带 ȣ���մϴ�.
�� �޼��忡���� ���� �� ��ü�� mountComponent() �޼��带 ȣ���ϸ�, �� ������ �ֿ� �۾��� ���۵˴ϴ�.

�ֿ� �۾���... ����!

App ������Ʈ�� �����Ǹ� <div> ������Ʈ�� �����մϴ�.
<div> ������Ʈ�� ���� ���� DOM�� �Բ� ReactDOMComopnent ��ü�� �����Ǹ� �ֿ� �۾��� ������ �����ϴ�.

* ���� DOM�� ����
* style �Ӽ��� attr �Ӽ� �߰�
* ��ġ ó�� �۾��� ����� �̺�Ʈ ���
���...


+render() �Լ��� ȣ���ϴ� ����� store�� ������� �� Virtual DOM�� �����ϴ� ����Դϴ�.

�� �ڴ� �������... ������ ���...
���� https://d2.naver.com/helloworld/9297403