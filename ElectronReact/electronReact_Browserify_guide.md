React + Electron + Browserify Start guide
=========================================
Electron과 React를 사용하여  멀티플랫폼 데스크톱 앱을 만들기 위한 개발 환경및 배포방법을 작성한 문서입니다.(Browserify)
**Browserify**
Node.js 기반 javascript code 를 브라우저 환경에서도 실행 가능하도록 만들어주는 라이브러리이다.
React 및 jQuery와 같은 클라이언트 JS 라이브러리를 Node와 함께 require()사용하여 번들링을 쉽게합니다.

## 작업 환경 설정방법

1. project 생성

2. ```npm install -g browserify``` 설치

3. 프로젝트폴더에 ```.babelrc```파일 생성하여 하단과 같이 작성
  ```
  {
    "presets" : ["es2015"]
  }
  ```

4. ```npm init``` 명령어 실행하여 package.json파일 생성

5. package.json 파일에서 scripts부분 수정
```
"scripts": {
    "start": "electron main.js",
    "watch": "watchify app/app.js -t babelify -o public/js/bundle.js --debug --verbose"
```

6. package.json 파일에서 dependencies 부분 수정
```
"dependencies": {
    "babel-preset-es2015": "^6.6.0",
    "babel-preset-react": "^6.5.0",
    "babelify": "^7.2.0",
    "classnames": "^2.2.3",
    "electron-prebuilt": "^0.36.0",
    "electron-reload": "^0.2.0",
    "jquery": "^2.2.3",
    "react": "^0.14.8",
    "react-autocomplete": "^1.0.0-rc2",
    "react-dom": "^0.14.7",
  }
```
5. ```npm install```명령어를 실행한후 package 설치

6.  ```index.html```파일 생성 후 하단의 소스 작성
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <body>

    <div id="content"></div>

  <script src="public/js/bundle.js"></script>
  </body>
</html>
```
7.
