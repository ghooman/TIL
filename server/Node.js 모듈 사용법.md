# 📌 Node.js 모듈 사용법

>Node.js는 로컬 환경에서 자바스크립트를 실행할 수 있는 자바스크립트 런타임이다.   
그리고 Node.js는 브라우저에서 불가능한 몇 가지 일이 가능하다.   

💡모듈?   
건축으로부터 비롯된 모듈이라는 단어는, 어떤 기능을 조립할 수 있는 형태로 만든 부분이다. fs(File System) 모듈은, PC의 파일을 읽거나 저장하는 등의 일을 할 수 있게 도와준다.   

💡Node.js 내장 모듈 목록은 다음 링크에서 찾을 수 있다.   
https://nodejs.org/dist/latest-v14.x/docs/api/   

모든 모듈은 '모듈을 사용하기 위해 불러오는 과정'이 필요합니다. 브라우저에서 다른 파일을 불러올 때에는 다음과 같이 <script> 태그를 이용했다.   
```html
<script src="불러오고싶은_스크립트.js"></script>
```

Node.js 에서는 자바스크립트 코드 가장 상단에 require 구문을 이용하여 다른 파일을 불러온다.   
```javascript
const fs = require('fs'); // 파일 시스템 모듈을 불러옵니다
const dns = require('dns'); // DNS 모듈을 불러옵니다

// 이제 fs.readFile 메소드 등을 사용할 수 있습니다.
```
---
# 📌 3rd-party 모듈을 사용하는 방법
서드 파티 모듈(3rd-party module)은 해당 프로그래밍 언어에서 공식적으로 제공하는 빌트인 모듈(built-in module)이 아닌 모든 외부 모듈을 일컫는다.   
예를 들어, Node.js에서 underscore는 Node.js 공식 문서에 없는 모듈이기 때문에 서드 파티 모듈이다. underscore 와 같은 서드 파티 모듈을 다운로드하기 위해서는 npm을 사용해야 한다.   

터미널에서 다음과 같이 입력해 underscore 를 설치할 수 있다.
```
npm install underscore
```

이제 node_modules에 underscore가 설치되었다. 이제 Node.js 내장 모듈을 사용하듯 require 구문을 통해 underscore 를 사용할 수 있다.   
```javascript
const _ = require('underscore');
```
