# async await

## async 와 await 은 뭔가요?
자바스크립트의 비동기 처리 패턴입니다.
setTimeout, callback, promise의 단점 보완

js는 싱글 스레드 프로그래밍언어이기 때문에 비동기처리가 필수적입니다.
(비동기 처리는 결과가 언제 반환될 지 알 수 없기 때문)


## 사용방법
사용방법은 간단합니다.
* function 키워드 앞에 <b>async</b>만 붙여줍니다.
* 비동기로 처리되는 부분 앞에 <b>await</b>를 붙여주면 됩니다.

```javascript
async function example(num){
     const num = await getNum(num);
}
```

* aync 함수가 호출되면 Prmoise 리턴
async함수에서 값을 리턴하면, promise는 그 값을 받아서 resolved됩니다. async함수는 await 표현식을 포함하고 있으며 async 함수에 Promise 값이 전달되기 전까지 실행을 지연시킵니다. 

오늘은 여기까지,,