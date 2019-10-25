# history

react는 single page application으로, 한페이지만 사용하는 특성상, 새로고침 할 일이 없어야 합니다.

그래서 URL이동이 새로 고침을 사용하는 다중 페이지를 사용하는 경우와 다릅니다.

URL 이동시키기
? Link : 새로고침 없이 다른 뷰를 렌더 할 때 사용합니다.
a태그와 비슷하지만 새로고침X

? history.push : Route는 컴포넌트에 <b>기본적으로 match, history, location</b>을 넘겨줍니다.
이때 histroy.push(‘/이동할 위치’)를 넣어주면 해당 인자로 url을 새로고침 없이 이동시켜줍니다.

## history의 특징
* 브라우저의 window.history 와 유사
* 주소를 임의로 변경하거나 되돌아 갈 수 있도록 한다.
* 주소 변경시, SPA 특성을 지키기 위해 페이지 전체를 리로드 하지 않는다.
* location 이 포함되어 있다.

## location의 특징
* 브라우저의 window.location 와 유사
* 현재 페이지 정보를 지니고 있다.
* url의 query 정보를 search라는 프로퍼티에 가지고 있다.

## match의 특징
* Route의 path에 정의한 것과 매칭된 정보를 가지고 있다.
* params 에 설정한 파라미터를 담고 있다.

출처: https://medium.com/@han7096/react-router-v4-%EC%A0%95%EB%A6%AC-e9931b63dcae