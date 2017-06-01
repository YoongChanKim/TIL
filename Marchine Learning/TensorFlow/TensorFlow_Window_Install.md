TensorFlow Windows Install
==========================
Windows 64비트 환경에 TensorFlow를 쉽게 설치할 수 있는 방법이다.


## 1. Python 설치
Windows에서 TensorFlow가 Python 3.5 이상부터 동작하기 때문에 __꼭 Python 3.5 이상의  버전을 설치__ 해야 한다.

* Downloads

https://www.python.org/downloads/release/python-353/

__설치는 디폴트로 설정되어 있는 그대로 진행 한다.__


## 2. Anaconda 설치하기
현재 윈도우 환경에서 제공되고 있는 Anaconda 최신 버전을 다운로드 한다.

* Downloads

https://www.continuum.io/downloads

### 설치시 유의사항

- 1. __Python 3.5 버전__ 을 다운로드 해야 한다.
- 2. 다운로드된 exe 파일을 열 때 __관리자 권한__ 으로 실행한다.
- 3. 디폴트로 설정돼 있는 값에 따라 설치한다.
- 4. 설치 후 Anaconda prompt를 관리자 권한으로 실행한다.


## 3. TensorFlow 설치
Anaconda prompt에서 TensorFlow를 설치하기 위해서 3개의 명령어를 작성 해야한다.

### 설치방법

#### 1. pip 업그레이드 하기
```
# python -m pip install --upgrade pip
```

#### 2. Conda 환경 만들기
```
Conda create -n tensorflow python=3.5

Proceed(y/n)? y
```

#### 3. TensorFlow 설치하기
```
activate tensorflow

# 프롬프트가 'tensorflow'로 바뀜
(tensorflow)>pip install tensorflow
```

### 참고 문서

- https://brunch.co.kr/@mapthecity/15
