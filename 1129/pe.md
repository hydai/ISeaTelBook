#10301 	PE -Thank Hydai
##出題者：
Name: henry

Mail: henryyang42@gmail.com
##出題目的&解題方法：
中和前兩題需要轉一下的題目，這題只需要單純的印出幾次的字串就可以了。不要忘了換行符號要放上去。

##解題所需要的關鍵：
標準輸出，迴圈。

##解題程式碼：
```C
#include <stdio.h>
int main() {
    int t, space = 0;
    scanf("%d", &t);
    while(t--) {
        if (space++) putchar(10);
        int n, i;
        scanf("%d", &n);
        for (i = 0; i < n; i++) {
            puts("Hydai is god!");
        }
    }
    return 0;
}
```
