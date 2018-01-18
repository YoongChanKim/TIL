디폴트 매개변수
==============
함수를 만들 때 매개변수의 디폴트 값을 지정할 수 있다.

```
class Date
{
  int year, month, day;
  void SetDate(int y = 1999, int m = 12, int d = 24);
};

void Date::SetDate(int y, int m, int d)
{
  year = y;
  month = m;
  day = d;
}
```
위와 같이 SetDate라는 멤버 함수를 선언할 때, 매개변수에 각각 1999, 12, 24리나느 디폴트 값을 지정했다. 이렇게 하면 SetDate 함수는 다음고 같이 호출이 가능하다.

```
Date date;
date.SetDate(); //1999, 12, 24을 지정
date.SetDate(2018); //2018, 12, 24을 지정
date.SetDate(2018, 4); //2018, 4, 24을 지정
date.SetDate(2018, 4, 27);//2018, 4, 27을 지정
```
즉, 매개변수를 지정해도 되고 지정하지 않아도 되는 것이다. 매개 변수를 지정하지 않으면 함수를 선언할 때 지정한 디폴드 값이 사용된다.
