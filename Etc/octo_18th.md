# axios 사용법

* Promise 기반의 HTTP 클라이언트로 javascript 라이브러리입니다.

## 특징
* 브라우저에서 XMLHttpRequest를 만듭니다.
* node.js로 http reauest들을 만듭니다.
* request, response
* request와 response 데이터 변환
* request 취소
* JSON 데이터를 위한 자동 변환
* axios는 Promise를 기반으로 하며, async/await 문법을 사용하여 XHR요청을 쉽게 할 수 있습니다.

### 설치
```javascript
//나는 지금 npm을 사용하고 있으니까~!
$ npm install axios
```

### 사용방법
```javascript
//post 요청 보내기
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```

### //이거 사용해야해
```javascript
// GET request for remote image
axios({
  method: 'get',
  url: 'http://bit.ly/2mTM3nY',
  responseType: 'stream'
})
  .then(function (response) {
    response.data.pipe(fs.createWriteStream('ada_lovelace.jpg'))
  });
```

이렇게 함수가 제공되서, 사용하기 좀 편리하긴 하더라구요

axios.request(config)
axios.get(url[, config])
axios.delete(url[, config])
axios.head(url[, config])
axios.options(url[, config])
axios.post(url[, data[, config]])
axios.put(url[, data[, config]])
axios.patch(url[, data[, config]])

### instance 생성해서 사용하기
```javscript
const instance = axios.create({
  baseURL: 'https://some-domain.com/api/',
  timeout: 1000,
  headers: {'X-Custom-Header': 'foobar'}
});

instance.get(~~);
```
내일 계속...