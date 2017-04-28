error – problem connecting in Linux XRDP
========================================
xrdp를 설치 하고 Windows에서 mstsc(원격 데스크톱)를 사용할 때 원격으로 접속이 되지 않은 에러 해결 방법
- error_message
  ```
  connecting to sesman ip 127.0.0.1 port 3350
  sesman connect ok
  sending login info to session manager, please wait...
  xrdp_mm_process_login_response: login successful for display...
  started connecting
  connecting to 127.0.0.1 5910
  error – problem connecting
  ```

 - 해결방법
 하단의 명령어 작성
  * xrdp 삭제
  ```
  sudo apt-get remove xrdp
  ```
  * tightvncserver 설치
  ```
  sudo apt-get install tightvncserver
  ```
  * xrdp 설치
  ```
  sudo apt-get install xrdp
  ```

출처: http://nancom.tistory.com/173 [나다니엘과 컴퓨터]
