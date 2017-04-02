# Electron-packager(build)
Electron-packager는 Electron을 이용하여 작성된 프로젝트를, 더 이상 개발환경에서 실행하지 않고, Standard alone으로 실행할 수 있는 파일로 만들어줌

```
npm install electron-packager --save-dev

// publishing
electron-packager <sourcedir> <appname> --platform=<platform> --arch=<arch> [optional flags...]
```

여기서 appname은 package.json에 정의된 name을 사용해야함(그렇지 않으면 프로젝트를 못 찾는 것 같다)
platform과 arch를 설정할 수 있다.(arch는 cpu 아키텍처를 의미한다)(리눅스에서 cpu아키텍처 확인은 터미널에서 cpu /proc/info)

##### 지원 platform
- darwin
- linux
- win32
- all

##### 지원 arch
- ie32
- x64
- armv7l
- all

예를 들어 이렇게 사용한다.

```
electron-packager . Reactron --platform=linux --arch=armv7l
```
위 명령어는 armv7l기반의 linux에서 도는 실행파일로 배포해준다.


https://github.com/electron-userland/electron-packager
