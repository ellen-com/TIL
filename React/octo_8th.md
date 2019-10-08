# WebPack

React를 사용할 때 WebPack 얘기가 많이 나오는데, 대체 뭘까… 싶었어서 정리합니다~

## WebPack 개념
웹팩을 알려면, 일단 모듈 번들러를 알아야 합니다.
모듈 번들러는 여러개의 나누어져 있는 파일들을 하나의 파일로 만들어주는 라이브러리를 의미합니다.
이 모듈 번들러 중 하나가 WebPack입니다.

## 어떻게 사용하면 되나요?
webpack을 설치하기 위해서는 Node.js와 npm을 먼저 설치해야 합니다.

웹팩의 주요 네가지 개념
### entry
간단하게 웹팩에서 시작점이라고 생각하면 됩니다.

웹팩에서 모든 것은 모듈입니다. js, css, img 등 모든 것을 자바스크립트 모듈로 로딩해서 사용합니다.
웹팩은 엔트리를 통해서 필요한 모듈을 로딩하고, 하나의 파일로 묶는다.

ex)
```javascript
entry: {
	main : ‘./src/index.js’,
}
```
이때, html에서 사용할 자바스크립트의 시작점은 src/index.js입니다.
entry 키에 시작점 경로를 지정합니다.

### output
엔트리에 설정한 자바스크립트 파일을 시작으로 의존되어 있는 모든 모듈을 하나로 묶습니다.
output은 번들된 결과물을 처리하는 위치입니다.
ex)
```javascript
output: {filename: ‘bundle.js’ },
```
bundle.js 파일로 결과를 저장한다는 것입니다.
html파일에서는 번들링 된 이 파일을 로딩하게 합니다.

### loader
웹팩은 모든 파일을 모듈로 관리합니다.
하지만 웹팩은 자바스크립트 밖에 모르기에, 비 자바스크립트 파일을 웹팩이 알 수 있게 바꿔줘야하는데 이를 로더가 합니다.

로더는 사용해보지 않아서 잘 모르겠습니다…

### plugin
로더가 파일단위로 처리하는 반면, 플러그인은 번들된 결과물을 처리합니다.

플러그인 설정중에 HtmlWebPlugin이 유명하므로 살짝 소개하려 합니다.
```javascript
	- plugins:[
		new HtmlWebpackPlugin({
			template: 'src/static/index.html',
			filename: 'index.html',
			inject: 'body',
		}),
],
```
plugins : plugin들을 설정하는 부분입니다. HtmlWebPackPlugin을 사용하였습니다.
HtmlWebPackPlugin의 template : 복사하는 파일의 경로를 나타냅니다. 
HtmlWebPackPlugin의 filename : template의 파일을 붙여넣을 파일의 경로를 나타냅니다. 
즉 template에서 filename으로 번들 된 파일이 <script />로 추된 html 파일이 복사됩니다. ./src/index.html 파일이 ./dist/index.html로 복사됩니다,


아… 역시 설정하는 부분이 제일 어려운 거 같네요…

