submodule(서브모듈)
=========
프로젝트를 수행하다 보면 다른 프로젝트를 함께 사용해야 하는 경우가 있다. 함께 사용할 다른 프로젝트는 외부에서 개발한 라이브러리던가 내부 여러 프로젝트에서 공통으로 사용할 라이브러리일 수 있다. 이러한 상황에서 자주 생긴는 이슈는 두 프로젝트를 서로 별개로 다루면서도 그 중 하나를 다른 하나안에서 사용할 수 있도록 하는 모듈이다.

__즉, git 저장소 안에 다른 git 저장소를 디렉토리로 분리해 넣는 것이 서브모듈이다. 다른 독립된 git 저장소를 clone 해서 내 git 저장소 안에 포함할 수 있으며 각 저장소의 커밋은 독립적으로 관리한다.__

## 서브모듈 사용방법
작업할 git 저장소에 미리 준비된 리모트 git 저장소를 서브모듈로 추가하는 명령을 작성한다.
```
git submodule add 추가할 저장소의 url
```

ex)
```
$ git submodule add https://github.com/chaconinc/DbConnector
Cloning into 'DbConnector'...
remote: Counting objects: 11, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 11 (delta 0), reused 11 (delta 0)
Unpacking objects: 100% (11/11), done.
Checking connectivity... done.
```
기본적으로 서브모듈은 프로젝트 저장소의 이름으로 디렉토리를 만든다. 만약 원하는 이름이 있다면 원하는 이름을 넣어 다른 디렉토리 이름으로 서브모듈을 추가 할 수 있다.  

추가가 되었는지 확인하는 방법
```
git status
```
명령어를 작성하면은 .gitmodules라는 파일이 생성되는 것을 볼 수 있다.

## 서브모듈을 포함한 프로젝트 clone
