# axios ����

* Promise ����� HTTP Ŭ���̾�Ʈ�� javascript ���̺귯���Դϴ�.

## Ư¡
* ���������� XMLHttpRequest�� ����ϴ�.
* node.js�� http reauest���� ����ϴ�.
* request, response
* request�� response ������ ��ȯ
* request ���
* JSON �����͸� ���� �ڵ� ��ȯ
* axios�� Promise�� ������� �ϸ�, async/await ������ ����Ͽ� XHR��û�� ���� �� �� �ֽ��ϴ�.

### ��ġ
```javascript
//���� ���� npm�� ����ϰ� �����ϱ�~!
$ npm install axios
```

### �����
```javascript
//post ��û ������
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```

### //�̰� ����ؾ���
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

�̷��� �Լ��� �����Ǽ�, ����ϱ� �� ���ϱ� �ϴ��󱸿�

axios.request(config)
axios.get(url[, config])
axios.delete(url[, config])
axios.head(url[, config])
axios.options(url[, config])
axios.post(url[, data[, config]])
axios.put(url[, data[, config]])
axios.patch(url[, data[, config]])

### instance �����ؼ� ����ϱ�
```javscript
const instance = axios.create({
  baseURL: 'https://some-domain.com/api/',
  timeout: 1000,
  headers: {'X-Custom-Header': 'foobar'}
});

instance.get(~~);
```
���� ���...