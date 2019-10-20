# Axios

������ Request Config�� �����Ƿ� ������ Response Schema~

## Response Schema

```javascript
{
  // �����κ��� �������� response
  data: {},
 
  //  ���� �������� ���� ���� HTTP status code
  status: 200,
 
  // ���� �������κ��� ���� HTTP status message
  statusText: 'OK',
 
  // �����κ��� ������� ������, ��� ��� �̸��� �ҹ��� �Դϴ�.
  headers: {},
 
  // ��û�� ���� axios�� �����Ǵ� ����
  config: {},
 
  // �� ������ ������ ��û
  // �������� XMLHttpRequest �ν��Ͻ�
  request: {}
}
```

## then

then�� ����ϸ� �Ʒ��� ���� ������� ���� �� �־��

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

### Global axios �⺻��
```javascript
axios.defaults.baseURL = 'https://api.example.com';
axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;
axios.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded';
```

### Custom instance �⺻����
```javascript
// �ν��Ͻ��� ������ �� �⺻ ����
const instance = axios.create({
  baseURL: 'https://api.example.com'
});
 
// �ν��Ͻ� �����ϰ� �⺻�� �ٲٱ�
instance.defaults.headers.common['Authorization'] = AUTH_TOKEN;
```


## Handling Errors
���� ������ ���� ó������

```javascript
axios.get('/user/12345')
  .catch(function (error) {
    if (error.response) {
      // ��û�� ������ ��, ������ �����ڵ�� ������ ������
      console.log(error.response.data);
      console.log(error.response.status);
      console.log(error.response.headers);
    } else if (error.request) {
      //��û�� �������� ������ ������
      // error.request�� ���������� XMLHttpRequest�� �ν��Ͻ�
      console.log(error.request);
    } else {
      // request�� �����ϴ� �߿� ������ �߻���
      console.log('Error', error.message);
    }
    console.log(error.config);
  });
```


```javascript
//�̷��� ���� ó������ ���� ����.
axios.get('/user/12345', {
  validateStatus: function (status) {
    return status < 500;than or equal to 500
  }
})
```