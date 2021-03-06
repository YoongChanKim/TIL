객체 지향 프로그래밍(Object Oriented Programming)
============================================
객체지향 프로그래밍이란 프로그램을 만들 때 이 세상의 Object를 프로그램을 구성하는 기본 단위로해서 프로그래밍을 하겠다는 의미이다.

## 객체지향 프로그래밍의 이해
객체는 상태와 행동으로 이루어진 것이라고 생각하면 된다. 자동차를 예로 들면 자동차의 속도,기름양 등이 __상태__ 가 될 수 있고, 속도를 올리거나 속도를 내리거나 혹은 기름을 채우거나, 채우지 않는것 등의 동작은 __행동__ 입니다. 위와 같이 __상태__ 와 __행동__ 으로 이루어진 것을 __객체__ 라고 말할 수 있다.

### 객채지향 프로그램의 구성단위
C++에서는 클래스가 프로그램을 이루는 기본단위 이다. 객체지향적으로 프로그램을 작성 할 때는 기능적인 측면에서 세분하는 것이 아니라 프로그램을 구성하는 __오브젝트단위로 세분화__ 한다. 그런 다음 각각의 오브젝트를 클래스로 구현한다. 즉, 함수를 이용하여 프로그램이 수행해야 할 기능을 만들듯이, 클래스를 이용하면 오브젝트를 표현할 수 있다.

### C와 C++ 프로그래밍 구조 비교

#### C                              
* 절차지향 프로그래밍(구조적)         

* 프로그램을 기능 단위로 세분         

* 함수로 이루어짐                    

* 소형, 중형 프로그램 작성에 적합       

#### C++  
* 객체지향 프로그래밍

* 프로그램을 오브젝트 단위로 세분

* 클래스로 이루어짐

* 대형 프로그램 작성에 적합

### 객체지향 프로그래밍의 예
계산기를 예로 들어 볼 때 C와 C++의 차이를 비교해 보면 쉽게 할 수 있다.

#### C
계산기를 기능에 따라 세분

* 입력기능 - Input(){ }
* 계산기능 - Compute(){ }
* 출력기능 - Output() { }

각각의 기능을 함수로 구현

#### C++
계산기를 구성하는 오브젝트로 세분

* Keyboard - class Keyboard{ };
* Display - class Display{ };
* CPU - class CPU{ };

각각의 오브잭트를 클래스로 구현
