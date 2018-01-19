const 변수 / 함수
=================
변수 이름 앞 또는 함수 이름 뒤에 const 키워드를 붙일 수 있다. const를 변수 이름 앞에 붙이면 그 변수 값을 변경할 수 없게되고, 함수 이름 뒤에 const를 붙이면 그 함수 내에서 변수의 값을 변경할 수 없다.

## const 변수
변수를 선언할 때 앞에 const 키워드를 붙여주면 값을 초기화 할 수는 있지만, 그 이후에 값을 변경할 수 없는 상수가 된다.

```
const double pi = 3.141592;
pi = 10 //에러! 상수는 변수처럼 값을 바꿀 수 없다.
```
프로그래머가 변경하지 말아야 하는 값을 실수로 변경하는 것을 막을 수 있다.

## const 멤버 함수
클래스의 멤버 함수를 선언할 때 함수 선언 뒤에 const를 붙여주면 그 함수는 변수의 값을 변경할 수 없다.

```
class Count
{
  public:
    int GetCount() const;
    void SetCount(int nCount);

  private:
   int m_nCount;
};

int Count::GetCount() const
{
  return m_nCount;
}

void Count::SetCount(int nCount)
{
  m_nCount = nCount; // 멤버변수의 값 변경
}
```
SetCount 함수는 매개변수로 넘겨받은 값을 이용하여 멤버 변수 m_nCount의 값을 변경하는 기능을 한다. 하지만 GetCount 함수는 멤버 변수 m_nCount의 값을 참조는 하지만, 변경할 일은 없다. const 함수에서 멤버 변수의 값을 변경하면 컴파일 하다가 에러가 발생하기 때문에 프로그래머가 실수로 멤버 변수의 값을 변경하는 것을 막을 수 있다.
