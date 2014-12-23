#10322 	PC - 費式數列與矩陣快速冪

##出題者：
Name: hydai

Mail: z54981220@gmail.com

##出題目的：
本題主要希望透過提示的方式讓大家學會如何使用快速冪。

##解題方法：
直接修改範例程式碼，把原本是數字的地方變成矩陣的乘法（公式也在題目中有給）

只要在過程中注意不要不小心 overflow（要 mod）以及矩陣乘法時寫對。

##解題所需要的關鍵：
矩陣乘法，運用範例程式碼

##解題程式碼：
```cpp
#include <iostream>

using namespace std;
typedef unsigned long long T;
const T MOD = 100000007;
class Matrix {
private:
    T data[2][2];
public:
    Matrix() {
        for (int i = 0; i < 2; i++)
            for (int j = 0; j < 2; j++)
                data[i][j] = 0;
    }
    Matrix(T old[2][2]) {
        for (int i = 0; i < 2; i++)
            for (int j = 0; j < 2; j++)
                data[i][j] = old[i][j];
    }
    Matrix operator* (const Matrix &mul) {
        Matrix ret;
        ret.data[0][0] = (this->data[0][0]*mul.data[0][0]+this->data[0][1]*mul.data[1][0])%MOD;
        ret.data[0][1] = (this->data[0][0]*mul.data[0][1]+this->data[0][1]*mul.data[1][1])%MOD;
        ret.data[1][0] = (this->data[1][0]*mul.data[0][0]+this->data[1][1]*mul.data[1][0])%MOD;
        ret.data[1][1] = (this->data[1][0]*mul.data[0][1]+this->data[1][1]*mul.data[1][1])%MOD;
        return ret;
    }
    T getAns() {
        return this->data[0][1];
    }
};
T fib(T n) {
    T data[2][2] = {{1, 1}, {1, 0}};
    Matrix tmp(data);
    data[0][1] = 0; data[1][0] = 0; data[1][1] = 1;
    Matrix ans(data);
    while(n) {
        if (n & 1) {
            ans = ans*tmp;
        }
        tmp = tmp*tmp;
        n = n >> 1;
    }
    return ans.getAns();
}
int main(int argc, char *argv[])
{
    T n;
    while (cin >> n) {
        cout << fib(n) << endl;
    }
    return 0;
}
```
