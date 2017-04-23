Sphinx(스핑크스) - Python 문서화
===============================
Sphinx는 Python 코드 내에 들어간 docstring을 자동으로 문서화해주는 도구이며 아주 간단한 설정만 끝내면 손쉽게 문서를 만들 수 있다.

## 스핑크스(Sphinx) 설치 및 실행

1. 스핑크스 Doc 설치

```
$ sudo pip install Sphinx
```
만약, 설치시 오류가 발생한다면 ```pip```버전이 낮아서 발생할 가능성잉 크다. 따라서 pip를 업그레이드해서 다시 인스톨하면 된다.

```
$ easy_install pip
$ pip install --upgrade setuptools
```

2. 특정 폴더에 ```myPKG.tgz```을 해제

```
$ mkdir ~/sphinx_doc
$ cd ~/sphinx_doc
$ tar xvfz myPKG.tgz
```

3. 파이썬 패스 추가
스핑크스를 기동시키는데 해당 모듈이 접근 가능해야 한다.

```
$ export PYTHONPATH=$PYTHONPATH:~/sphinx_doc
```

4. 모듈의 클래스 or 함수등의 API 생성

```
$ cd ~/sphinx_doc
$ sphinx-apidoc -F -f -o apidoc myPKG
```

5. 실제 html 문서 생성

```
$ cd ~/sphinx_doc/apidoc
$ make html
```

__주의 : 위와 같이 하면 디폴트로 파이썬 모듈의 소스가 포함된다. 이를 포함 안 시키려면__

```
$ cd ~/sphinx_doc/apidoc
$ vi conf.py
```

'sphinx.ext.viewcode'부분을 #으로 코멘트를 막고 저장 후```$ make html``` 명령어 작성
```
extensions = [
    'sphinx.ext.autodoc',
#    'sphinx.ext.viewcode',
]
```

## 테마 변경
스핑크스는 다양한 테마를 지원하고 쉽게 테마를 변경할 수도 있다. ```conf.py``` 파일 안에
```
html_theme = 'classic'
```
스핑크스가 지원하는 테마에 따라 수정하면 된다. 예)alabaster, sphinx_rtd_theme 등 ..

## 스핑크스(Sphinx) 문법

#### 모듈 설명
모듈 설명은 소스코드 제일 상단에 모듈의 전체적인 이해를 위해 작성하는 문서이다.

```
"""
====================================
 :mod:`mod2` 모듈2
====================================
.. moduleauthor:: 홍길동 <gdhong@foo.org>
.. note:: Future's NDA License

설명
=====

이 mod2 모듈은 스핑크스 문서화를 위한 테스트 입니다

참고
====

참고:
 * http://sphinx-doc.org/
 * http://docutils.sourceforge.net/rst.html

관련 작업자
===========

본 모듈은 다음과 같은 사람들이 관여했습니다:
 * 개발2실 홍길동
 * 개발2실 둘리

작업일지
--------

다음과 같은 작업 사항이 있었습니다:
 * [2023/22/22] - 함수AAA 추가
 * [2023/22/02] - 본 모듈 작업 시작
"""
```

#### 클래스 설명
문서화 될 내용은 항상 해당 클래스, 함수, 전역변수 선언 아래 줄부터 작성한다.

```
class XScanEngine (object) :
    '''XScanEngine 클래스

    모든 검사 엔진들은 XScanEngine 클래스를 반드시 상속 받아야 한다.

    예제 :

        >>> class HWP3(XScanEngine) :
        ...
    '''
위의 결과물이 아래의 그림이다.
```

#### 함수 설명
함수를 설명할 때에는 인자값, 리턴값등을 추가한다. 이때 사용되는 키워드는 ```:param:```, ```:returns:```이다.

```
@abstractmethod
    def GetPPSTree(self) :
        '''
        분석 대상 파일의 내부 Tree 구조를 리턴하는 가상함수이다.

        Tree 구조는 다음과 같다.

        * ['1', '2', '3'] : 1, 2, 3 모두 스트림임
        * [['1', ['2']], '3'] : 1은 소토리지이며 1 하위에 2 스트림이 존재함

        :returns list: tree - 파일 내부 Tree 구조를 표현한 리스트
        '''
        raise NotImplementedError
```

##### 참고 문서

http://www.hanul93.com/python-sphinx/
http://m.egloos.zum.com/mcchae/v/11080328
https://b.ssut.me/python-문서화-sphinx-로-시작하기/
