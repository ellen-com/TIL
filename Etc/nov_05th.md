# stream

JDK 8���� �߰��� Stream API�� ���ؼ� �˾ƺ���.(���� I/O���� ���Ǵ� ��Ʈ������ �ٸ���) ��Ʈ���� �����ͼҽ��� �߻�ȭ�ϰ�, �����͸� �ٷ�µ� ���� ���Ǵ� �޼����� ������ ���Ҵ�. �����ͼҽ��� �߻�ȭ�Ͽ��ٴ� ����, ������ �ҽ��� �����̵� ���� ������� �ٷ� �� �ְ� �Ǿ��ٴ� �Ͱ� �ڵ��� ���뼺�� �������ٴ� ���� �ǹ��Ѵ�. 

## ��Ʈ�� ������ ���ǻ��� 

��Ʈ���� ������ ũ�� 3������ ������.

<b>��Ʈ������ -> �߰� ���� -> ��������</b>
 // �����ϱ� -> �����ϱ� -> ��������

-> "Collections���� ��ü ����.��Ʈ������().�߰�����().��������();"

* .���� ������ �� �ְ� �ϴ� ����� �����������̶�� �Ѵ�.


����
```javascript
//Stream ��� ��
String[] strArr = { "mash-up", "backend", "codingsquid" }

Arrays.sort(strArr);

for(String str: strArr) {
  System.out.println(str);
}

//Stream ��� ��
Stream<String> listStream = strList.stream();

listStream.sorted().forEach(System.out::println);
```

## ��Ʈ�������ϱ�

### �÷���
�ڹٿ��� �����ϴ� ��� �÷����� �ְ� ���� ������ Collection �������̽����� stream() �޼ҵ尡 ���ǵǾ� �ֽ��ϴ�.
���� Collection �������̽��� ������ ��� List�� Set �÷��� Ŭ���������� stream() �޼ҵ�� ��Ʈ���� ������ �� �ֽ��ϴ�.
����, parallelStream() �޼ҵ带 ����ϸ� ���� ó���� ������ ��Ʈ���� ������ �� �ֽ��ϴ�.

����
```javascript
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(4); list.add(2); list.add(3); list.add(1);

// �÷��ǿ��� ��Ʈ�� ����
Stream<Integer> stream = list.stream();

// forEach() �޼ҵ带 �̿��� ��Ʈ�� ����� ���� ����
stream.forEach(System.out::println);
```

### �迭
�迭�� ���� ��Ʈ���� �����ϱ� ���� Arrays Ŭ�������� �پ��� ������ stream() �޼ҵ尡 Ŭ���� �޼ҵ�� ���ǵǾ� �ֽ��ϴ�.
����, �⺻ Ÿ���� int, long, double ���� ������ �� �ִ� �迭�� ���� ��Ʈ���� ������ ���ǵǾ� �ֽ��ϴ�.
�̷��� ��Ʈ���� java.util.stream ��Ű���� IntStream, LongStream, DoubleStream �������̽��� ���� �����˴ϴ�.

```javascript
String[] arr = new String[]{"��", "��", "��", "�ϳ�"};

// �迭���� ��Ʈ�� ����
Stream<String> stream1 = Arrays.stream(arr);
stream1.forEach(e -> System.out.print(e + " ")); 

// �迭�� Ư�� �κи��� �̿��� ��Ʈ�� ����
Stream<String> stream2 = Arrays.stream(arr, 1, 3);
stream2.forEach(e -> System.out.print(e + " "));
```

## ���� ǥ����
���� ǥ������ �Ű������� ���޹޾� �ش� ���� ǥ���Ŀ� ���� ��ȯ�Ǵ� ���� ��ҷ� �ϴ� ���� ��Ʈ���� �����ϱ� ���� Stream Ŭ�������� iterate()�� generate() �޼ҵ尡 ���ǵǾ� �ֽ��ϴ�. 
iterate() �޼ҵ�� �õ�(seed)�� ��õ� ���� ���� ǥ���Ŀ� ����Ͽ� ��ȯ�� ���� �ٽ� �õ�� ����ϴ� ������� ���� ��Ʈ���� �����մϴ�.
�ݸ鿡 generate() �޼ҵ�� �Ű������� ���� ���� ǥ������ ����Ͽ� ��ȯ�� ������ ���� ��Ʈ���� �����մϴ�.
���� ������ iterate() �޼ҵ带 �̿��Ͽ� Ȧ�������� �̷���� ���� ��Ʈ���� �����ϴ� �����Դϴ�.

```javascript
IntStream stream = Stream.iterate(2, n -> n + 2); // 2, 4, 6, 8, 10, ...
```