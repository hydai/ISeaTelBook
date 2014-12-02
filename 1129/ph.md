#10316 	PH - Porblem of Lian D & Ko P
##出題者：
Name: andyw330

Mail: andyw330@gmail.com

##出題目的＆解題方法：
費氏數列，只是需要注意如果超過 2147483647 就印出字串，檢查的時候要小心，如果越界就會變成負的值。

##解題所需要的關鍵：
迴圈。

##解題程式碼：
```CPP
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    long long int ans[100] = {0};
    for (int i = 0; i < 100; i++) {
        ans[i] = -1;
    }

    ans[0] = ans[1] = ans[2] = 1;
    for (int i = 3; i <= 90; i++) {
        ans[i] = ans[i-1]+ans[i-2];
        if (ans[i] > 2147483647) {
            ans[i] = -1;
            break;
        }
    }
    int t;
    cin >> t;
    while (t--) {
        int q;
        cin >> q;
        if (ans[q] != -1) {
            cout << ans[q] << endl;
        } else {
            cout << "Don't make Sean unhappy!" << endl;
        }
    }
    return 0;
}
```
