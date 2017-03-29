React.js 작업환경 설정
====================
Node.js 환경에서 React를 사용할 때의 작업환경 설정에 대한 내용이며
webpack 과 browserify를 이용하는 방법이 있다.

**webpack을 사용할 것 입니다.**

## 1. Nodejs 및 npm 설치

  **하단의 링크 참조**

  Link : [nodejs,npm instll]: https://github.com/YoongChanKim/TIL/blob/master/Javascript/Nodejs/nodejs_config.md

  * node js를 설치한 후
  ```
  $ npm install -g npm
  # 최신버전으로  업데이트 해주는 명령어
  ```

## 2. Global Package 설치
작업환경을 만들기 위해 몇가지 global 패키지가 설치 되어야 한다.
  ```
  $ npm install -g babel webpack webpack-dev-server
  ```
  1. babel – 아직 ECMAScript6 를 지원하지 않는 환경에서 ECMAScript6 Syntax를 사용 할 수 있게 해줍니다.

  2. webpack – 모듈 번들러로서, Browserify 처럼 브라우저 위에서 import (require) 을 할 수 있게 해주고 자바스크립트 파일들을 하나로 합쳐줍니다.

  3. webpack-dev-server – wepback에서 지원하는 간단한 개발서버로서 별도의 서버를 구축하지 않고도 웹서버를 열 수 있으며 hot-loader를 통하여 코드가 수정될때마다 자동으로 리로드 되게 할 수 있습니다.

## 3. Project 생성
디렉토리 생성후 npm init 명령어를 사용하면 Node.js프로젝트 생성이 된다.
```
$ mkdir project-name
$ cd project-name
$ npm init
```

## 4. Dependency 및 Plugin 설치

  * react 패키지 설치

  React를 사용할 것이기 때문에 React 패키지를 설치해 주어야 한다.
  ```
  $ npm install --save react react-dom
  ```

  * babel 플러그인 설치

  babel 에서 사용 될 플러그인을 설치해 주어야 한다.
  개발환경에서만 사용되므로 --save-dev옵션을 설정해준다.
  ```
  $ npm install --save-dev babel-core babel-loader babel-preset-react babel-preset-es2015 webpack webpack-dev-server
  ```
  > webpack 과 webpack-dev-server 가 글로벌로 이미 설치가 되어있는데,
  로컬 모듈로 설치된 이유는 webpack 의 livereload와 비슷한 기능인 –hot 옵션을 사용하기 위함 입니다. 사실 상, webpack 모듈을 글로벌 패키지로서 꼭 설치 할 필요는 없습니다. 이를 설치 한 이유는 커맨드라인에서 webpack-dev-server을 바로 실행하기 위함인데, 로컬에만 설치하고 나중에 webpack 을 실행할 때는 ./node_modules/bin/webpack-dev-server –hot 이런식으로 실행 할 수 있습니다.
