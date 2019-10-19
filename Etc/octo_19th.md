# Axios

method: post�̶�� �� �� ������, axios���� �����ϴ� .post �Լ��� ����� ���� �ֽ��ϴ�.

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
    //��û�� �� ����� URL ����
    url: '/person',

    //��û �� �� ���Ǵ� ��� 
    method: 'get',

    //�̷��� �����صΰ�, �ν��Ͻ� ���� ����ϸ� ����
    baseURL: 'https://some-domain.com/api/',

    //������ ������ ���� request data�� �ٲ��ݴϴ�~
    transformRequest: [function (data, headers) {
	//������ �˾Ƽ� �ٲټ�~!
	return data;
    }],

    //������� �����͸� �ٲ��ݴϴ�
    transformResponse: [function (data) {
	//������ �˾Ƽ� �ٲټ�~!
	return data;
    }],

    //���� �� ����� Ŀ���� ���
    headers: {'X-Requested-With': 'XMLHttpRequest'},

    //request�� ���� �� ���Ǵ� URL �Ķ���͵�
    //plain object �ƴ� URLSearchParams object�� ����ؾ���
    params: {
	ID: 12345
    },

    // request body�� ������ ����
    //PUT, POST, PATCH������ ��밡��
    //transformRequest�� ������� ������, �Ʒ� Ÿ�� �� �ϳ��� �ݵ�� ����ؾ� ��
    // - string, plain object, ArrayBuffer, ArrayBufferView, URLSearchParams
    // - Browser only: FormData, File, Blob
    // - Node only: Stream, Buffer
    data: {
	firstName: 'Fred'
    },

    //request time out
    timeout: 1000, //�⺻���� 0


    responseType: 'json', //�⺻���� ���̽�

    responseEncoding: 'utf8', //�⺻��

}
```

����� �ֻ�.
���� : https://www.npmjs.com/package/axios