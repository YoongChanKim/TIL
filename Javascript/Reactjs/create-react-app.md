create-react-app
================
React 작업환경을 명령어 하나로 설정 할 수 있는 "공식도구"에 대한 내용을 담고 있습니다.
webpack / babel 등을 설정하는 시간을 줄여줄 수 있습니다.

## create-react-app 설치
```
$ npm install -g create-react-app
```
* 글로벌 패키지를 설치합니다. Node 버전은 4.x 이상이여야 합니다.

## App 생성
```
  $ create-react-app project-name
  ```
  * create-react-app 도구를 이용하여 react 프로젝트를 생성할 수 있습니다.

  * 자동으로 스크립트를 통하여 dependency package 들을 설치합니다. (webpack babel eslint 등..)
  * dependency package 를 루트 프로젝트에 설치되지 않고 node_modules/react-scripts 디렉토리에 설치합니다.

## Production 을 위한 빌드
  ```
  $ npm run bulid
  ```
  * 코드가 minify 되고, envify 되고, 또 assets에 content hashes 를 통하여 캐싱이 적용됩니다.

## 도구 Eject
  ```
  $ npm run eject
  ```
  * 이 도구의 개발자는 create-react-app으로 생생된 프로젝트를 자신의 환경에 맞게 변경할 수 있게 합니다.

### 참고문서

https://velopert.com/2037  
