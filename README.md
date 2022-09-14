# Node.js
Node.js

VScode Terminal 이용


Node.js 패키지 생성 및 실행 - Node.js package, npm init, npm run   ::: https://carrotweb.tistory.com/107  

Node.js의 패키지 만들기
 - 폴더 생성
 - 콘솔에서 생성된 폴더로 이동
 - 패키지를 생성하기 위해 npm init 명령어를 실행
 - 폴더에 package.json 파일이 생성됩니다.
D:\_nodejs\nodePjt>
D:\_nodejs\nodePjt>npm init

{
  "name": "test1",
  "version": "1.0.0",
  "description": "test",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "carrotweb",
  "license": "ISC"
}

* 패키지를 설치하는 명령어입니다.
  Express.js 설치하기
  Express.js는 Node.js에서 HTTP와 관련된 컴포넌트를 기반으로 하는 웹 애플리케이션 프레임워크입니다.
  현재 패키지(애플리케이션)에 Express.js를 설치하기 위해 콘솔에서 npm install 명령어를 실행합니다.
  npm install에 옵션으로 --save를 추가하면 자동으로 package.json 파일의 "dependencies"에 "express" 항목이 추가됩니다.
D:\_nodejs\nodePjt>
D:\_nodejs\nodePjt>npm install express --save

{
  "name": "test1",
  "version": "1.0.0",
  "description": "test",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "carrotweb",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1" --> 추가
  }
}


 * Node.js의 패키지(애플리케이션) 실행하기
 * Node.js를 종료는 콘솔에서 Ctrl + C를 누르면 됩니다.

D:\_nodejs\nodePjt>
D:\_nodejs\nodePjt>node index.js
Listening...
^C
D:\_nodejs\nodePjt>^C
D:\_nodejs\nodePjt>

=========================================================


접속 : http://localhost:8080/index.html


* npm으로 실행하기 위해 Script 추가하기
* 콘솔에서 npm start를 실행합니다.
  종료하려면 콘솔에서 Ctrl + C를 누르고 "Y"를 입력하고 엔터키를 누르면 됩니다.

D:\_nodejs\nodePjt>npm run start
npm WARN config global `--global`, `--local` are deprecated. Use `--location=global` instead.

> nodepjt@1.0.0 start
> node index.js

Listening...


* Express 정적 파일 적용하기
 - index.js를 오픈하여 이미지 파일이나 CSS 파일, JavaScript 파일 등과 같은 정적 파일을 제공하기 위해 
   Express.js의 express.static() 메서드를 추가합니다. 정적 파일들이 들어있는 폴더로 public 폴더를 설정하였습니다.
 - 폴더에 public 폴더를 생성합니다.
 - public 폴더에 index.html 파일을 생성합니다.
 - npm start를 실행합니다.
   
   D:\_nodejs\nodePjt>npm run start

 - 브라우저에서 "http://localhost:8080/index.html"를 입력

 * webpack build 
npm 으로 webpack build 하려고 하는 경우,
package.json 에서 "build" : "webpack" 으로 변경하면, npm 에서 webpack을 찾아 실행한다.
(build 안에 npm 명령어 모두 명시안해도 작동한다.)

D:\_nodejs\nodePjt>npx webpack serve

> npm run build

 webpack.config.js 에서 static, port 만 있으면 된다. 

  devServer: {
    //contentBase: path.resolve("./build"),
    //index: "index.html",
    static:"./",
    port: 8080
