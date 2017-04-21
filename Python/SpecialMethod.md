Python의 특별한 메서드
=====================
메서드는 클래스를 만들면서 그 안에 만들어 넣은 함수를 말한다. 메서드를 사용하려면 객체.메서드()형식으로 호출하는 것과 다르게 Python 에서 앞뒤로 __ 가 붙어 있는 변수나 함수는 특정 용도로 미리 정의해 둔 메서드 이다.


## ```__init__``` Method (초기화)
```
class Music:

    def setData(self, title, artist, album):
        self.title = title
        self.artist = artist
        self.album = album

    def printData(self):
        print '노래 제목 : ', self.title
        print '아티스트 : ', self.artist
        print '앨범 : ', self.album

    def __init__(self):
      self.setData(title, price, author)
        print '노래 객체를 새로 만들었다!'
```
예제로 Music(음악) 클래스를 갖는 musisdata(음악정보) 모듈을 만들었다.

음악 클래스의 메서드는 노래 제목,아티스트, 앨범과 같은 자료들을 입력할 때 사용할 setData()와 이런 자료들을 출력해주는 printData()를 만들어 주었다.

마지막 줄에 ```__init__``` 메소드가 있다. 이 메소드는 초기화(Initialize) 메소드 라고 한다. 이 메소드는 어떤 클래스의 객체가 만들어질 때 자동으로 호출되어서 그 개체가 갖게 될 여러 가지 성질을 전해주는 일을 한다.
참고) 초기화 메서드와 같은 것을 다른 객체지향 언어에서는 생성자(constructor)라고 부른다.

## ```__del__``` Method (소멸자)

```__init__``` 메서드와 반대로 객체가 없어질 대 호출되는 메서드 이다. 이런 것을 소멸자(destructor)라고 한다. 파이썬에서는 ```__del__``` 메소드가 소멸자 역활을 한다. ```__del__```문은 만들어 둔 객체각 더 이상 필요 없어지면 파이썬이 알아서 처리해주기도 한다. 즉, ```__del__```문을 사용하는 이유는 어떤 객체가 없어지기 전에 뭔가 처리를 필요로 할 때 사용한다.


### 참고 문서

출처: http://felixblog.tistory.com/58 [오늘, 행복하자!]
