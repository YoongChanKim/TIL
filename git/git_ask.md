git/github 관련 질문
===================

### 1. git과 github의 차이점
```
git은 각 컴퓨터(local)에 설치되어 소스코드관리가 가능한 프로그램이고
github는 remote저장소가 있는 외부서버를 지칭한다.
```

### 2. commit과 push의 차이점
```
commit 은 local 작업폴더에 history 를 쌓는것이어서 외부망을 안쓰고
Push는 remote 저장소 (Github 등..)에 history 를 쌓는것이어서 외부망이 필요하다.
```

### 3. fetch와 pull의 차이점
```
Remote 저장소 (Github 등..)로 부터 최신 commit 정보들을 가져오는것은 같지만
Fetch 는 가져와서 임시폴더 (.git)에 저장하고
Pull 은 바로 현재 branch 에 merge 작업을 동반한다.
```

### 4. rebase 와 merge의 차이점
```
둘다 두 branch 의 차이점 (commits) 를 합치는것은 같지만
Rebase 는 합치기 전에 되감기 (rewinding) 를 하고
Merge 는 안하고 합친다 .
```
