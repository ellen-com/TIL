# Stream
## Stream이란 무엇인가?

* 배열, 컬렉션 인스턴스에 함수 여러개를 조합해서 원하는 결과를 필터링 -> 가공된 결과
* 람다를 이용해서 코드의 양을 줄이고 간결하게 표현 가능. -> 배열과 컬렉션을 함수형으로 처리할 수 있음.
* 간단하게 병렬처리(multi-threading) 가능

## Stream은 크게 세가지로 나뉠 수 있다.
1. 생성하기 : 스트림 인스턴스 생성
2. 가공하기 : 필터링 or 매핑 등 원하는 결과를 만들어가는 중간 작업
3. 결과 만들기 : 최종적으로 결과를 만들어내는 작업

``` 전체 -> 맵핑 -> 필터링1 -> 필터링2 -> 결과 만들기 -> 결과 ```

### 생성하기
보통 배열과 컬렉션을 이용해서 스트림을 만들지만 이 외에도 다양한 방법으로 스트림을 만들 수 있음.

#### 배열 스트림
스트림을 사용하기 위해 가장 먼저 해야 할 것은 <strong>생성</strong>
배열, 컬렉션 등의 인스턴스로 스트림 생성 가능
```java
String[] arr = new String[]{"a", "b", "c"};
Stream<String> stream = Arrays.stream(arr);
Stream<String> streamOfArrayPart = 
Arrays.stream(arr, 1, 3);
```
#### 컬렉션 스트림
컬렉션 타입(Collection, List, Set)의 경우 인터페이스에 디폴트 메소드 stream이 있으므로, 이를 이용해 stream 생성
```java
public interface Collection<E> extends Iterable<E> {
default Stream<E> stream() {
return StreamSupport.stream(spliterator(), false);
} 
// ...
}
```
#### Stream.builder()
빌더(Builder)를 사용하면 스트림에 직접적으로 원하는 값을 넣을 수 있음. 마지막에 build 메소드로 스트림을 리턴합니다.
```
Stream<String> builderStream =
Stream.<String>builder()
.add("A").add("B").add("C")
.build(); // [A, B, C]
```

#### Stream.generate()
generate 메소드를 이용하면 Supplier<T> 에 해당하는 람다로 값을 넣을 수 있습니다.
```python
//다시 공부해서 보충하기
```
