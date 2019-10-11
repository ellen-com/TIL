#ES6
ES6�� ECMAScript6��� �Ҹ���, �ڹٽ�ũ��Ʈ ����� ǥ���Դϴ�.

## ȭ��ǥ �Լ�
```javascript
//�Ű����� ���� ���
() => {} //�Ű�����X
x => {} // �Ű������� �ϳ��� ���, �Ұ�ȣ ���� ����
(x, y) => {}

// �Լ� ��ü ���� ���
x => { return x * x }
x => x * x  // �Լ� ��ü�� ������ �����̶�� �߰�ȣ�� ������ �� ������ �Ϲ������� return�ȴ�. �� ǥ���� ����

() => { return { a: 1 }; }
() => ({ a: 1 })  // �� ǥ���� ����. ��ü ��ȯ�� �Ұ�ȣ�� ����Ѵ�.

() => { //�������� ���
  const x = 10;
  return x * x;
};
```
ȭ��ǥ �Լ��� ȣ��
```javascript
const pow = x => x * x;
// const pow = �Ű����� x, x*x���� ��ȯ
```

```javascript
// ES6
const arr = [1, 2, 3];
const pow = arr.map(x => x * x);

console.log(pow); // [ 1, 4, 9 ]
```

ȭ��ǥ �Լ������� this�� ���� �������� this�� ����Ų��.
```javascript
window.x = 1;
const normal = function () { return this.x; };
const arrow = () => this.x;

console.log(normal.call({ x: 10 })); // 10
console.log(arrow.call({ x: 10 }));  // 1
```

[����] https://poiemaweb.com/es6-arrow-function

## ����
����� �� �ִ� �����δ� const, let, var�� ������, var�� ������� �ʽ��ϴ�.
* const : ���� �����Ǹ� ���߿� �ٲ� �� �����ϴ�.
* let : ���� �����Ǿ ���߿� ���� �ٲ� �� �ֽ��ϴ�.

## Modules
export, import�� �̿��� function�̳� ������ �ٸ� ������ ����� �� �ֽ��ϴ�.

```javascript
// exportEx.js
export const exportFunc = (x) => {return x*x}

//importEx.js
import { exportFunc } from "exportEx"
console.log(exportFunc(3)) //9
```

## Promise
�̰� ���� �ẻ �� ��� ������ �� �𸣰ڽ��ϴ�.

�񵿱� ���μ����� ���� ���˴ϴ�. (Asynchronously)
�������� ������ ��ø�� �ݹ��� ������ ��ȭ�մϴ�.
(Callback Hell�̶�� Callback �Լ��� �ٽ� Callback�� ȣ���ϰ� �Ǵٽ� Callback�� ȣ���ϴ� �ڵ带 �б⵵ �����ϱ⵵ ��������� ���� ��ȭ�� �� �ֽ��ϴ�.)

Promise�� ������ ����

�����(pending)
�����(fulfilled)
�źε�(rejected)
����ϳ׿�. ��ó : http://woowabros.github.io/experience/2017/12/01/es6-experience.html