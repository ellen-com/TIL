# stream

JDK 8에서 추가된 Stream API에 대해서 알아보자.(파일 I/O에서 사용되는 스트림과는 다르다) 스트림은 데이터소스를 추상화하고, 데이터를 다루는데 자주 사용되는 메서들을 정의해 놓았다. 데이터소스를 추상화하였다는 것은, 데이터 소스가 무엇이든 같은 방식으로 다룰 수 있게 되었다는 것과 코드의 재사용성이 높아진다는 것을 의미한다. 

## 스트림 사용법과 주의사항 

스트림의 구조는 크게 3가지로 나뉜다.

<b>스트림생성 -> 중개 연산 -> 최종연산</b>
 // 생성하기 -> 가공하기 -> 결과만들기

-> "Collections같은 객체 집합.스트림생성().중개연산().최종연산();"

* .으로 연계할 수 있게 하는 방법을 파이프라인이라고도 한다.


예시
```javascript
//Stream 사용 전
String[] strArr = { "mash-up", "backend", "codingsquid" }

Arrays.sort(strArr);

for(String str: strArr) {
  System.out.println(str);
}

//Stream 사용 후
Stream<String> listStream = strList.stream();

listStream.sorted().forEach(System.out::println);
```

## 스트림생성하기

### 컬렉션
자바에서 제공하는 모든 컬렉션의 최고 상위 조상인 Collection 인터페이스에는 stream() 메소드가 정의되어 있습니다.
따라서 Collection 인터페이스를 구현한 모든 List와 Set 컬렉션 클래스에서도 stream() 메소드로 스트림을 생성할 수 있습니다.
또한, parallelStream() 메소드를 사용하면 병렬 처리가 가능한 스트림을 생성할 수 있습니다.

예제
```javascript
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(4); list.add(2); list.add(3); list.add(1);

// 컬렉션에서 스트림 생성
Stream<Integer> stream = list.stream();

// forEach() 메소드를 이용한 스트림 요소의 순차 접근
stream.forEach(System.out::println);
```

### 배열
배열에 관한 스트림을 생성하기 위해 Arrays 클래스에는 다양한 형태의 stream() 메소드가 클래스 메소드로 정의되어 있습니다.
또한, 기본 타입인 int, long, double 형을 저장할 수 있는 배열에 관한 스트림이 별도로 정의되어 있습니다.
이러한 스트림은 java.util.stream 패키지의 IntStream, LongStream, DoubleStream 인터페이스로 각각 제공됩니다.

```javascript
String[] arr = new String[]{"넷", "둘", "셋", "하나"};

// 배열에서 스트림 생성
Stream<String> stream1 = Arrays.stream(arr);
stream1.forEach(e -> System.out.print(e + " ")); 

// 배열의 특정 부분만을 이용한 스트림 생성
Stream<String> stream2 = Arrays.stream(arr, 1, 3);
stream2.forEach(e -> System.out.print(e + " "));
```

## 람다 표현식
람다 표현식을 매개변수로 전달받아 해당 람다 표현식에 의해 반환되는 값을 요소로 하는 무한 스트림을 생성하기 위해 Stream 클래스에는 iterate()와 generate() 메소드가 정의되어 있습니다. 
iterate() 메소드는 시드(seed)로 명시된 값을 람다 표현식에 사용하여 반환된 값을 다시 시드로 사용하는 방식으로 무한 스트림을 생성합니다.
반면에 generate() 메소드는 매개변수가 없는 람다 표현식을 사용하여 반환된 값으로 무한 스트림을 생성합니다.
다음 예제는 iterate() 메소드를 이용하여 홀수만으로 이루어진 무한 스트림을 생성하는 예제입니다.

```javascript
IntStream stream = Stream.iterate(2, n -> n + 2); // 2, 4, 6, 8, 10, ...
```