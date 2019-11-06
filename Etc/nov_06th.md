# Java Stream 중간연산
어제에 이어서... 중간연산(가공하기)를 해봅시다.

## Filtering
필터(filter)은 스트림 내 요소들을 하나씩 평가해서 걸러내는 작업입니다. 인자로 받는 Predicate 는 boolean 을 리턴하는 함수형 인터페이스로 평가식이 들어가게 됩니다.

```javascript
Stream<String> stream = 
  names.stream()
  .filter(name -> name.contains("a"));
   //‘a’ 가 들어간 이름만 들어간 스트림이 리턴됩니다.
```

## Mapping

맵(map)은 스트림 내 요소들을 하나씩 특정 값으로 변환해줍니다. 이 때 값을 변환하기 위한 람다를 인자로 받습니다.

스트림에 들어가 있는 값이 input 이 되어서 특정 로직을 거친 후 output 이 되어 (리턴되는) 새로운 스트림에 담기게 됩니다. 이러한 작업을 맵핑(mapping)이라고 합니다.

```javascript
Stream<String> stream = 
  names.stream()
  .map(String::toUpperCase);
   //toUpperCase 메소드를 실행해서 대문자로 변환한 값들이 담긴 스트림을 리턴합니다.
```

```javascript
Stream<Integer> stream = 
  productList.stream()
  .map(Product::getAmount);
   //요소 내 들어있는 Product 개체의 수량을 꺼내올 수도 있습니다. 각 ‘상품’을 ‘상품의 수량’으로 맵핑하는거죠.
```

### flatMap
```javascript
<R> Stream<R> flatMap(Function<? super T, ? extends Stream<? extends R>> mapper);
```
인자로 mapper를 받고 있는데, 리턴 타입이 Stream 입니다. 즉, 새로운 스트림을 생성해서 리턴하는 람다를 넘겨야합니다. flatMap 은 중첩 구조를 한 단계 제거하고 단일 컬렉션으로 만들어주는 역할을 합니다. 이러한 작업을 플래트닝(flattening)이라고 합니다.


```javascript
List<List<String>> list = 
  Arrays.asList(Arrays.asList("a"), 
                Arrays.asList("b"));

List<String> flatList = 
  list.stream()
  .flatMap(Collection::stream)
  .collect(Collectors.toList());
// [a, b]
```

객체에도 사용 가능
```javascript
students.stream()
  .flatMapToInt(student -> 
                IntStream.of(student.getKor(), 
                             student.getEng(), 
                             student.getMath()))
  .average().ifPresent(avg -> 
                       System.out.println(Math.round(avg * 10)/10.0));
```

## Sorting
말해 뭐해 정렬

```javascript
IntStream.of(14, 11, 20, 39, 23)
  .sorted()
  .boxed()
  .collect(Collectors.toList());
// [11, 14, 20, 23, 39]

List<String> lang = 
  Arrays.asList("Java", "Scala", "Groovy", "Python", "Go", "Swift");

lang.stream()
  .sorted()
  .collect(Collectors.toList());
// [Go, Groovy, Java, Python, Scala, Swift]

lang.stream()
  .sorted(Comparator.reverseOrder())
  .collect(Collectors.toList());
// [Swift, Scala, Python, Java, Groovy, Go]
```