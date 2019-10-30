# MobX state tree

* store(mst���� ���¸� ������ ���� object)���� observable property���� ����
* React.component���� <b>observer</b>�� ���ָ� �� ����� �ٽ� page rendering�� �̷����
   -> ��Ȯ�� ������ڸ� �ش� property�� ����ϴ� ���� ���� ����ȴ�

## store
* types.model�� ����
* object�� �ٵ� JSON object�� �޶� .toJS()�� �̿��ؼ� ����ؾ� console.log�� �� ����

## action
action���� ���� �޾Ƽ� �������� �� observer�� ������ ������ ����ϴ��� ����� �� �� �� �����Ƿ� �����ϸ� view�� ����Ϸ���

// view�� �����ϱ�

```
types.model�� ���� �д°� ��𼭵� ���������� �����ϴ� ���� �ش� model ���� action������ �����ϴ�. �̰� �θ� tree�� �ڽ� tree�� ����������. �׷��� �ܺο��� �����ؾ��ϴ� property�� ���ؼ��� action�� setter�� �����ؾ� �Ѵ�.
```

���� : https://devstarsj.github.io/development/2019/05/19/mobx-state-tree.usage/

���� ���..