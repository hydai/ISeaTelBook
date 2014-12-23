#10344 	PD - 海帶的書櫃
##出題者：
Name: henry

Mail: henryyang42@gmail.com

##出題目的：
本題的核心思想是想出 counting，把每一筆出現過的 key 都算一下次數，然後輸出。

##解題方法：
把一串英文讀入以後，只取三個合起來當成是 key 。
每次拿到一把 key 以後就更新 key list ，最後輸出 list 的 size 即可。

##解題所需要的關鍵：
Counting

##解題程式碼：
```c
#include <stdio.h>
#define PENDING 128
#define HSIZE 26*10000+26*100+26+PENDING
char inputBuffer[128];
int  hashMap[HSIZE];
int  dis[3] = {1, 100, 10000};
char toU(char in) {
    if (in > 'Z')
        return in - 'a' + 'A';
    else
        return in;
}
int main(int argc, char *argv[]) {
    int T;
    scanf("%d", &T);
    while (T--) {
        int n;
        int hash, i;
        for(i = 0; i < HSIZE; i++)
            hashMap[i] = 0;
        scanf("%d", &n);
        while(n--) {
            hash = 0;
            for(i = 0; i < 3; i++) {
                scanf("%s", inputBuffer);
                hash += dis[i]*(toU(inputBuffer[0])-'A');
            }
            hashMap[hash]++;
        }
        int ans = 0;
        for(i = 0; i < HSIZE; i++) {
            if (hashMap[i] != 0) ans++;
        }
        printf("%d\n", ans);
    }
    return 0;
}
```
