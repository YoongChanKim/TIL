Music Player Daemon server guide
================================
## Music Player Daemon(MPD)?
MPD(Music Player Daemon)는 Linux에서 음악파일을 재생, 관리해주는 서비스이다. 스피커 출력, 네트워크 스트리밍을 지원할 뿐만 아니라 재생및 playlist 관리를 할 수 있는 프로그램입니다. 또한 원격관리가 가능 합니다.

## MPD Install and Setting

### Linux 기본 설정 및 설치
MPD를 설치하기 전에 기본적인 환경 설정을 한다.(아래의 링크 참조)
https://github.com/YoongChanKim/TIL/blob/master/MPD_RaspberryPi/Linux_Base_Setting.md

### MPD 설치 및 설정

* root 권한 얻기(계속 sudo를 치기귀찮아서 root에서 작업함)
```
$ sudo su
```

* Music Play Daemon(MPD) 설치
```
$ sudo apt-get install mpd
```

* MPD 설정 파일을 열어줍니다.
```
$ sudo vi /etc/mpd.conf
```

* Music Play Daemon(MPD) 설정

  **'#'은 주석을 의미 한다.**

  * Files and directories 설정
  ```
  14  music_directory		"/music"

  21  playlist_directory		"/music_playlists"

  29  db_file			"/var/lib/mpd/tag_cache"

  44  pid_file			"/run/mpd/pid"

  51  state_file			"/var/lib/mpd/state"

  56  sticker_file     "/var/lib/mpd/sticker.sql"
  ```

  * General music daemon options 설정
  ```
  68  user				"root"

  75  group       "root"

  84  bind_to_address		"any"

  92  port				"6600"

  122  metadata_to_use	"artist,album,title,track,name,genre,date,composer,performer,disc"

  127 auto_update    "yes"
  ```

  * input 설정
  ```
  193   input {
  194          plugin "curl"
  195   #       proxy "proxy.isp.com:8080"
  196   #       proxy_user "user"
  197   #       proxy_password "password"
  198   }
  ```

  * Audio Output 설정
  ```
  212   audio_output {
  213 	 type		"alsa"
  214 	 name		"My ALSA Device"
  215 	 device		"hw:0,1"	# optional
  216   #	mixer_type      "hardware"      # optional
  217   #	mixer_device	"default"	# optional
  218   #	mixer_control	"PCM"		# optional
  219   #	mixer_index	"0"		# optional
  220   }
  ```

  * Character Encoding 설정
  ```
  387   filesystem_charset		"UTF-8"

  391   id3v1_encoding			"UTF-8"
  ```
  **설정 저장후 재시작**
  * MPD 재시작
  ```
  $sudo /etc/init.d/mpd restart
  ```

  * MPD가 실행중인지 확인
  ```
   $ ps -ef | grep mpd
  ```
