#10297 	PB - สองบวกสี่เท่ากับหก
##出題者：
Name: hydai

Mail: z54981220@gmail.com

##出題目的：
測試同學在處理標準輸出入測試資料的方法。

##解題方法：
把輸入的數字加總並輸出就是答案。

由於保證運算過程不超過 `signed 32-bit int` 所以不需要使用 `long long int` 來處理。

##解題所需要的關鍵：
標準輸出入，迴圈。

##解題程式碼：
```c
#include <stdio.h>
int main(int argc, char *argv[])
{
    int n;
    scanf("%d", &n);
    while(n--) {
        int m;
        scanf("%d", &m);
        int ans = 0;
        while(m--) {
            int tmp;
            scanf("%d", &tmp);
            ans+=tmp;
        }
        printf("%d\n", ans);
    }
    return 0;
}
```
