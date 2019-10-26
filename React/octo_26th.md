# JSX

����Ʈ������ JSX��� �� ����մϴ�.
JSX�� ���� ������ �����ұ��մϴ�.

������ ���� ������ �͵� ���....

```javascript
const element = <h1>Hello, world!</h1>;
```
html�� ���� �� ������ JSX��, �ڹٽ�ũ��Ʈ�� ���� Ȯ���Դϴ�.

JSX�� React ��Ҹ� �����, �� ��Ҵ� DOM���� ������ �˴ϴ�.

## JSX �Ӽ�
�Ӽ��� �߰�ȣ�� �̿��� �ڹٽ�ũ��Ʈ ǥ������ ���Խ�ų �� �ֽ��ϴ�.
```javascript
const element = <img src={user.avatarUrl}></img>;
```
JSX�� HTML���ٴ� �ڹٽ�ũ��Ʈ�� ������ ������, React DOM�� HTML �Ӽ� �̸� ��� camelCase �Ӽ� �̸� �������� ����մϴ�.

## JSX ��ü ǥ��

Babel�� JSX�� React.createElement() ȣ��� �������ϱ� ������, �� ������ �����մϴ�.
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