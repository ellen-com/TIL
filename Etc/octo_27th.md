# meta 태그
<meta /> 태그는 웹 페이지의 보이지 않는 정보를 제공하는데 쓰이는 태그입니다.
페이지의 설명 요약, 핵심 키워드, 제작자, 크롤링 정책 등 수많은 정보를 제공할 수 있습니다.

<meta /> 태그를 이용하여 description, keywords, author, subject, classification 등의 정보를 표기할 수 있으며,
검색 엔진은 이런 정보를 적극적으로 활용합니다.

```html
<meta charset="utf-8">
	<!-- 웹 브라우저가 서버에 명령을 내리는 속성으로 name 속성을 대신하여 사용될 수 있으며, HTML 문서가 응답 헤더와 함께 웹 서버로부터 웹 브라우저에 전송되었을 때에만 의미를 갖습니다. -->
	<meta http-equiv="X-UA-Compatible" content="IE=edge">

	<!-- 검색 결과에 표시되는 문자를 지정 -->
	<meta name="description" content="태그는, 태그 내부에 값을 넣을 수 있을 뿐만 아니라, 태그마다 속성을 부여할 수 있습니다.">

	<!-- 홈페이지 주제를 지정 -->
	<meta name="subject" content="태그의 속성">

	<!-- 검색 엔진에 의해 검색되는 단어 지정-->
	<meta name="keywords" content="www,web,">
```

## og태그
```html
<!-- 필수 og 태그 -->
<meta property="og:title" content="meta태그란">
<meta property="og:description" content="사이트의 설명을 적어주는 og태그 입니다~ 필수태그에요~~~">
<!-- 사이트의 대표 이미지 지정 -->
<meta property="og:image" content="img.png">

<!-- 필수는 아닌 og 태그 -->
<!-- 사이트의 타입을 적어주는 og 태그 -->
<meta property="og:type" content="website">

<!-- 사이트의 URL을 적어주는 og 태그 -->
<meta property="og:url" content="https://github.com/ellen-com/TIL">
```