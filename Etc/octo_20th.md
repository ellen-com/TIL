# Axios

어제는 Request Config를 봤으므로 오늘은 Response Schema~

## Response Schema

```javascript
{
  // 서버로부터 제공받은 response
  data: {},
 
  //  서버 응답으로 부터 받은 HTTP status code
  status: 200,
 
  // 서버 응답으로부터 받은 HTTP status message
  statusText: 'OK',
 
  // 서버로부터 응답받은 헤더들로, 모든 헤더 이름은 소문자 입니다.
  headers: {},
 
  // 요청을 위해 axios에 제공되는 구성
  config: {},
 
  // 이 응답을 생성한 요청
  // 브라우저와 XMLHttpRequest 인스턴스
  request: {}
}
```

## then

then을 사용하면 아래와 같은 응답들을 받을 수 있어욤

```javascript
axios.get('/user/12345')
  .then(function (response) {
    console.log(response.data);
    console.log(response.status);
    console.log(response.statusText);
    console.log(response.headers);
    console.log(response.config);
  });
```

## Config Defaults

### Global axios 기본값
```javascript
axios.defaults.baseURL = 'https://api.example.com';
axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;
axios.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded';
```

### Custom instance 기본값들
```javascript
// 인스턴스를 생성할 때 기본 설정
const instance = axios.create({
  baseURL: 'https://api.example.com'
});
 
// 인스턴스 생성하고 기본값 바꾸긔
instance.defaults.headers.common['Authorization'] = AUTH_TOKEN;
```


## Handling Errors
에러 응답은 어케 처리하지

```javascript
axios.get('/user/12345')
  .catch(function (error) {
    if (error.response) {
      // 요청을 보냈을 때, 서버가 상태코드로 응답을 보내줌
      console.log(error.response.data);
      console.log(error.response.status);
      console.log(error.response.headers);
    } else if (error.request) {
      //요청을 보냈지만 응답은 없었음
      // error.request는 브라우저에서 XMLHttpRequest의 인스턴스
      console.log(error.request);
    } else {
      // request를 설정하는 중에 오류가 발생함
      console.log('Error', error.message);
    }
    console.log(error.config);
  });
```


```javascript
//이렇게 따로 처리해줄 수도 있음.
axios.get('/user/12345', {
  validateStatus: function (status) {
    return status < 500;than or equal to 500
  }
})
```