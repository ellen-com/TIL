# async await

## async �� await �� ������?
�ڹٽ�ũ��Ʈ�� �񵿱� ó�� �����Դϴ�.
setTimeout, callback, promise�� ���� ����

js�� �̱� ������ ���α׷��־���̱� ������ �񵿱�ó���� �ʼ����Դϴ�.
(�񵿱� ó���� ����� ���� ��ȯ�� �� �� �� ���� ����)


## �����
������� �����մϴ�.
* function Ű���� �տ� <b>async</b>�� �ٿ��ݴϴ�.
* �񵿱�� ó���Ǵ� �κ� �տ� <b>await</b>�� �ٿ��ָ� �˴ϴ�.

```javascript
async function example(num){
     const num = await getNum(num);
}
```

* aync �Լ��� ȣ��Ǹ� Prmoise ����
async�Լ����� ���� �����ϸ�, promise�� �� ���� �޾Ƽ� resolved�˴ϴ�. async�Լ��� await ǥ������ �����ϰ� ������ async �Լ��� Promise ���� ���޵Ǳ� ������ ������ ������ŵ�ϴ�. 

������ �������,,