# Axios

method: post이라고도 쓸 수 있지만, axios에서 제공하는 .post 함수를 사용할 수도 있습니다.

example
```javascript
const axios = require('axios');

axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

```javascript
{
    //요청할 때 사용할 URL 서버
    url: '/person',

    //요청 할 때 사용되는 방법 
    method: 'get',

    //이렇게 셋팅해두고, 인스턴스 만들어서 사용하면 편해
    baseURL: 'https://some-domain.com/api/',

    //서버로 보내기 전에 request data를 바꿔줍니다~
    transformRequest: [function (data, headers) {
	//데이터 알아서 바꾸셈~!
	return data;
    }],

    //응답받은 데이터를 바꿔줍니다
    transformResponse: [function (data) {
	//데이터 알아서 바꾸셈~!
	return data;
    }],

    //보낼 때 사용할 커스텀 헤더
    headers: {'X-Requested-With': 'XMLHttpRequest'},

    //request를 보낼 때 사용되는 URL 파라미터들
    //plain object 아님 URLSearchParams object로 사용해야함
    params: {
	ID: 12345
    },

    // request body로 데이터 전송
    //PUT, POST, PATCH에서만 사용가능
    //transformRequest를 사용하지 않으면, 아래 타입 중 하나를 반드시 사용해야 함
    // - string, plain object, ArrayBuffer, ArrayBufferView, URLSearchParams
    // - Browser only: FormData, File, Blob
    // - Node only: Stream, Buffer
    data: {
	firstName: 'Fred'
    },

    //request time out
    timeout: 1000, //기본값은 0


    responseType: 'json', //기본값이 제이슨

    responseEncoding: 'utf8', //기본값

}
```

등등이 있삼.
참고 : https://www.npmjs.com/package/axios