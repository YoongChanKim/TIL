Supervised Learning Basics
==========================
Supervised Learning(지도 학습)은 이미 레이블링이 된 데이터를 가지고 학습하는 것하는 학습방법이다. 예를 들어 사람이 강아지 이미지를 모아서 주고 그 이미지 데이터가 강아지라는 레이블이 달려있는 자료를 가지고 학습을 하는 것이다. 즉, 결과를 알려주고 학습을 시키는 방법이다.

Supervised Learning 의 경우는 라벨링된 데이터를 가지고 학습기를 학습시키는 경우를 말한다. 예를들어 학생의 공부시간에 따른 성적 분포에 대한 데이터가 있다면, 트레이닝 데이터 셋(Training data set)은 하단과 같은 모습을 뛸 수 있다.

__Training data set__

x (공부 시간) | y (성적)
---|---
8 | 90
6 | 70
4 | 50
2 | 30

상단의 표와 같이 특정 공부시간(x)에 해당하는 성적(y)에 대한 데이터를 학습시키는 것을 Supervised Learning(지도 학습)이라고 한다. 또한 Supervised Learning에 크게 3가지 유형(Type)이 있다.

## Supervised Learning 유형

### Regression
시험 준비에 투자한 시간에 따른 성적 분포 예측

data set 모습

x (공부 시간) | y (성적)
---|---
8 | 90
6 | 70
4 | 50
2 | 30

### Binary classification
시험 준비에 투자한 시간에 따른 Pass/Fail 두가지로 나눌 때

data set 모습     

x (공부 시간) | y (성적)
---|---
8 | pass
6 | pass
4 | fail
2 | fail

### multi-label classification
시험 준비에 투자한 시간에 따른 A, B, C, D, E..를 나눌 때

data set 모습

x (공부 시간) | y (성적)
---|---
8 | A
6 | B
4 | C
2 | D

#### 참고문서

* http://dev.limsee.com/?p=102
* https://www.youtube.com/watch?v=qPMeuL2LIqY
