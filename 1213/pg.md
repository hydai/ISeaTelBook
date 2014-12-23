#10362 	PG - Logic Design
##出題者：
Name: andy

Mail: andyw330@gmail.com

##出題目的：
本題是要大家練習一下 c/c++ 語言裡的一些邏輯運算。

##解題方法：
乖乖地照著圖把程式寫出來就可以拿到分數。

其實......他就是一個加法器，換句話說，寫出 A+B 的程式也能通關

##解題所需要的關鍵：
None.

##解題程式碼：
```c
#include<stdio.h>
int main (){
    int t;
    scanf("%d",&t);
    while (t--){
        int a,b;
        scanf("%d%d",&a,&b);
        printf("%d\n", a+b);
    }
    return 0;
}
```
