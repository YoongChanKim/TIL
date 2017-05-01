Linux 기본 설치및 설정
=====================

## 기본 설치 및 셋팅

### vim 설치및 설정 (vi 상향버전)

* vim 에디터 설치
```
sudo apt-get install vim
```

* vim 환경 설정
```
vi ~/.vimrc
```

* vim 설정파일을 열고 난 후에 i 키를 누릅니다.
* vim 기본 설정 파일에 하단의 명령어 입력 후 저장합니다.("는 주석을 뜻한다.)
```
set number            " line 표시를 해줍니다.
set ai                    " auto indent
set si                    " smart indent
set cindent            " c style indent
set shiftwidth=4      " shift를 4칸으로 ( >, >>, <, << 등의 명령어)
set tabstop=4         " tab을 4칸으로
set ignorecase      " 검색시 대소문자 구별하지않음
set hlsearch         " 검색시 하이라이트(색상 강조)
set expandtab       " tab 대신 띄어쓰기로
set background=dark  " 검정배경을 사용할 때, (이 색상에 맞춰 문법 하이라이트 색상이 달라집니다.)
set nocompatible   " 방향키로 이동가능
set fileencodings=utf-8,euc-kr    " 파일인코딩 형식 지정
set bs=indent,eol,start    " backspace 키 사용 가능
set history=1000    " 명령어에 대한 히스토리를 1000개까지
set ruler              " 상태표시줄에 커서의 위치 표시
set nobackup      " 백업파일을 만들지 않음
set title               " 제목을 표시
set showmatch    " 매칭되는 괄호를 보여줌
set nowrap         " 자동 줄바꿈 하지 않음
set wmnu           " tab 자동완성시 가능한 목록을 보여줌

syntax on        " 문법 하이라이트 킴"
```
**설치및 설정후 하단의 명령어 입력**

### 설치된 패키지 업데이트 및 업그레이드
```
sudo apt-get update
sudo apt-get upgrade  
```

### 한글 폰트 깨짐 현상 해결
```
sudo apt-get install ttf-unfonts-core
```
명령어 작업 후 reboot 한다.

출처: http://norux.me/13 [노루의 씨분투 세상]
