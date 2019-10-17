# useContext

useContext ������ ���ظ� �� �߾��µ�
������ ����ؼ� ���ظ� �ؾ߸� �մϴ�....
�ٽ� ���ϱ� �� �� �� �����󱸿�

useContext
```javascript
const value = useContext(MyContext);
```
context ��ü(React.createContext���� ��ȯ�� ��)�� �޾� �� context�� ���� ���� ��ȯ�մϴ�.
context�� ���� ���� Ʈ�� �ȿ��� �� Hook�� ȣ���ϴ� ������Ʈ�� ���� �����̿� �ִ� <MyContext.Provider>�� value prop�� ���� �����˴ϴ�.

������Ʈ���� ���� ����� <MyContext.Provider>�� ���ŵǸ� �� Hook�� �� MyContext provider���� ���޵� ���� �ֽ��� context value�� ����Ͽ� �������� Ʈ���� �մϴ�.

useContext�� ������ ���ڴ� context ��ü �� ��ü�̾�� �մϴ�.

�׷��� �� Context�� Provider�� �����ΰ�... �ϳĸ�

## Context.Provider
```javascript
<MyContext.Provider value={/* � �� */}>
```
Context ������Ʈ�� ���Ե� React ������Ʈ�� Provider�� context�� �����ϴ� ������Ʈ�鿡�� context�� ��ȭ�� �˸��� ������ �մϴ�.

Provider �� value prop�� �޾Ƽ� �� ���� ������ �ִ� ������Ʈ���� �����մϴ�.

Provider �������� context�� �����ϴ� ��� ������Ʈ�� Provider�� value prop�� �ٲ� ������ �ٽ� ������ �˴ϴ�.

## Context.Consumer
```javascript
<MyContext.Consumer>
  {value => /* context ���� �̿��� ������ */}
</MyContext.Consumer>
```
context ��ȭ�� �����ϴ� React ������Ʈ�Դϴ�.
�Լ� ������Ʈ�ȿ��� context�� �б� ���ؼ� �� �� �ֽ��ϴ�.

Context.Consumer�� �ڽ��� �Լ������մϴ�. �� �Լ��� context�� ���簪�� �ް� React ��带 ��ȯ�մϴ�. �� �Լ��� �޴� value �Ű����� ���� �ش� context�� Provider �� ���� Ʈ������ ���� ����� Provider�� value prop�� �����մϴ�. ������ Provider�� ���ٸ� value �Ű����� ���� createContext()�� ���´� defaultValue�� ������ ���Դϴ�.


��ó. reacts.org

�ƴ� �ٵ� ���� ���� �˰ڴµ� �� �����Ϸ��� ������󱸿� ����