this 포인터
===========
모든 클래스의 멤버 함수는 this라는 이름을 가진 특수한 용도의 포인터에 접근할 수 있다. this 포인터가 가리키는 것을 바로 자기 자신이다. 또한 this 포인터를 이용하여 현재 클래스의 인스턴스가 위치한 메모리의 주소를 알아 낼 수 있다.

## this 포인터의 용도
this 포인터는 여러 개의 클래스가 등장하는 약간 복잡하고 크기가 큰 프로그램을 작성할 때 주로 사용되기 때문에 예를 들기 힘들다. 설명하자면, 어떤 클래스의 멤버 함수 내에서 다른 클래스에 자기 자신을 매개변수로 넘겨줘야 할 필요가 있을 때 사용한다고 알아두면 좋다.

```
#include <iostream>

int val = 1;
class Number
{
private:
    int val = 0;
public:
    void add(int val)
    {
        this->val += val;
    }
    int getVal() { return this->val; }
};

int main(int argc, char** argv)
{
    Number num;
    num.add(3);

    printf("%d\n", num.getVal());
    return 0;
}
```
위와 같이 이름이 같은 변수를 연산을 할 때 매개변수와 클래스의 멤버변수라는 것을 확실히 구분하기 위해 클래스의 멤버변수에 this 포인터를 사용하여 구분한고 연산하는 것을 볼 수 있다.
