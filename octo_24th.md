# MobX

## Observable State
������ ���丸 �����ߴµ� �̹��� ��� ����ϴ� �� �˾ƺ��ô�.
�ֳĸ� ���� �̰� �����ؾ� �� �� ���ŵ��

���� �ϴ��� �� ������Ʈ�� ��� ����� ���� �־��µ�,
SRP ��Ģ��� �ϳ��� Ŭ������ �ϳ��� å�Ӹ� ������ �и��Ϸ��� �մϴ�.

������ React�� �ٸ� ������Ʈ���� ���� �ٲ� �� ���⿡...
MobX�� ����Ϸ��� �մϴ�.


```javascript
import { observable } from 'mobx';

//Observable State �����~!
const calculator = observable({
  a: 1,
  b: 2
});
```

Observable State�� ����ϸ� MobX�� �� ��ü�� �����Ͽ� <b>��ȭ�� ����</b>�մϴ�.


## reaction

```javascript
import { reaction } from 'mobx';

//calculator�� a ���� �ٲ� ������ �۾��ϱ�
reaction(
  () => calculator.a,
  (value, reaction) => {
    console.log(`reaction :: a �� = ${value}`);
  }
);
```


## computed
```javascript
// computed�� sum �� ĳ��! sum ���� �ٲ� �� ���� ����
const sum = computed(() => {
  console.log('������̿���!');
  return calculator.a + calculator.b;
});
```

# ES6�� ����ϸ� �� ����ϰ� �� �� �ִ��
�ٵ� ���� Ŭ������ ������� �ʰ� �־...
�̰� �� �����ϰ� �÷��߰ھ��

���� : https://velog.io/@velopert/begin-mobx