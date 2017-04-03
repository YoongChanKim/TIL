React + Electron + Webpack Start guide
============================
Electron과 React를 사용하여  멀티플랫폼 데스크톱 앱을 만들기 위한 개발 환경및 배포방법을 작성한 문서입니다.(Webpack)

## 작업 환경 설정방법

1. ```create-react-app```을 이용하여 Reactjs 프로젝트 생성 [create-react-app.md 링크 참조]
https://github.com/YoongChanKim/TIL/blob/master/Javascript/Reactjs/create-react-app.md

2. ```npm install --save-dev electron``` 설치

3. src폴더에```electron-starter.js```파일을 만들고 파일 안에 하단의 소스 copy & paste

  ```
  const electron = require('electron');
  // Module to control application life.
  const app = electron.app;
  // Module to create native browser window.
  const BrowserWindow = electron.BrowserWindow;

  const path = require('path');
  const url = require('url');

  // Keep a global reference of the window object, if you don't, the window will
  // be closed automatically when the JavaScript object is garbage collected.
  let mainWindow;

  function createWindow() {
      // Create the browser window.
      mainWindow = new BrowserWindow({width: 800, height: 600});

      // and load the index.html of the app.

      const startUrl = process.env.ELECTRON_START_URL || url.format({
              pathname: path.join(__dirname, '/../build/index.html'),
              protocol: 'file:',
              slashes: true
          });
      mainWindow.loadURL(startUrl);
    //  mainWindow.loadURL('http://localhost:3000');

      // Open the DevTools.
      mainWindow.webContents.openDevTools();

      // Emitted when the window is closed.
      mainWindow.on('closed', function () {
          // Dereference the window object, usually you would store windows
          // in an array if your app supports multi windows, this is the time
          // when you should delete the corresponding element.
          mainWindow = null
      })
  }

  // This method will be called when Electron has finished
  // initialization and is ready to create browser windows.
  // Some APIs can only be used after this event occurs.
  app.on('ready', createWindow);

  // Quit when all windows are closed.
  app.on('window-all-closed', function () {
      // On OS X it is common for applications and their menu bar
      // to stay active until the user quits explicitly with Cmd + Q
      if (process.platform !== 'darwin') {
          app.quit()
      }
  });

  app.on('activate', function () {
      // On OS X it's common to re-create a window in the app when the
      // dock icon is clicked and there are no other windows open.
      if (mainWindow === null) {
          createWindow()
      }
  });

  // In this file you can include the rest of your app's specific main process
  // code. You can also put them in separate files and require them here.
  ```
4. package.json 파일에```"main": "src/electron-starter.js"```를 추가

5. package.json 파일에 scripts부분에```"electron": "electron ."```를 추가

6. ```npm start``` 명령어, ```npm run dev```명령어를 작성 (Terminal를 2개 실행헤서 각각에 작성)

## React와 Electron을 동시에 실행 (더 편한 개발을 위한 옵션)

1. package.json 파일에```"homepage": "./",```를 추가

2. package.json 파일에 scripts부분에```"dev": "nf start -p 3000"```를 추가

3. ```npm install --save-dev foreman```명령어 작성

4. 프로젝트내의 가장 상위폴더에 Procfile 파일을 만들고 하단의 문장 copy & paste
  ```
  react: npm start
  electron: node src/electron-wait-react
  ```

5. src에 electron-wait-react.js파일을 만들고 하단의 소스 copy & paste
  ```
  const net = require('net');
  const port = process.env.PORT ? (process.env.PORT - 100) : 3000;
  process.env.ELECTRON_START_URL = `http://localhost:${port}`;
  const client = new net.Socket();
  let startedElectron = false;
  const tryConnection = () => client.connect({port: port}, () => {
          client.end();
          if(!startedElectron) {
              console.log('starting electron');
              startedElectron = true;
              const exec = require('child_process').exec;
              exec('npm run electron');
          }
      }
  );
  tryConnection();
  client.on('error', (error) => {
      setTimeout(tryConnection, 1000);
  });
  ```
  ** * 구문오류(syntax error)가 생길시 상단의 소스 맨위부분에 "use strict" 를 추가**

##  베포 방법
1. npm run build react를 배포파일로 빌드한다.

2. electron-packager를 사용해 electron 실행파일로 배포한다.( https://github.com/YoongChanKim/TIL/blob/master/ElectronReact/Electron_build.md 링크 참조)

### 관련 github 프로젝트

  * https://github.com/alanbsmith/react-electron-starter
  * https://github.com/christiannwamba/scotch-player
  * https://scotch.io/tutorials/build-a-music-player-with-react-electron-i-setup-basic-concepts (블로그)
