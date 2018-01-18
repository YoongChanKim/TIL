템플릿
======
템플릿을 이용하면 같은 형태를 갖는 클래스들을 줄줄이 찍어낼 수 있다. 데이터 형만 바뀌고 형태가 같은 클래스를 여러 가지로 찍어내고 싶으면 템플릿을 사용하면 된다.

## 템플릿을 이용한 클래스 선언
template이라는 키워드를 쓰고, <class type>이라고 적는다. 여기서 type은 앞으로 임의의 데이터 타입으로 대치될 문자 같은 것이다. 고정된 데이터 타입을 모두 대치가능한 type형으로 바꿔준다.
```
template <class type> class Point
{
  public:
    void SetPosition(type nX, type nY);
    void Move(type nX, type nY);
    void Show();

  protected:
    type m_nX, m_nY;
};
```

## 템플릿을 이용한 클래스 구현
클래스를 구현 할 때도 다음과 같이 비슷한 문법을 적용한다. 단, 템플릿을 이용할 때는 클래스의 구현을 소스 파일이 아닌 헤더파일에 적어야 한다.
```
template <class type>
void Point<type>::SetPosition(type nX, type nY)
{
  m_nX = nX;
  m_nY = nY;
}

template <class type>
void Point<type>::Move(type nX, type nY)
{

  m_nX += nX;
  m_nY += nY;
}

template <class type>
void Point<type>::Show()
{
  cout << "X=" << m_nX <<" Y=" << m_nY << endl;
}
```

## 템플릿을 이용한 클래스 활용
인스턴스를 만드는 순간에 다음과 같이 데이터 타이을 지정한다. 그러면 이전에 type이라는 문자가 모두 지정한데이터 타입으로 변환되어 지정한 데이터 타입에 맞는 클래스가 생성되고, 그 클래스가 동작을 하게 된다.
```
#include "Point.h"

void main()
{
  Point <double> dPosition;
  Point <int> iPosition;

  dPosition.SetPostion(12.34, 56.78);
  iPosition.SetPostion(12, 34);

  dPosition.Show();
  iPosition.Show();
}
```
