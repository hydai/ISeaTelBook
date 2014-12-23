#10360 	PF - Wrong Hole
##出題者：
Name: henry

Mail: henryyang42@gmail.com

##出題目的：
本題為滿足 henry 的惡作劇而出wwwwwwww

其實是在正式比賽中，我們曾經有過送錯題目的窘境，這樣的錯誤會讓你拿到罰分，可能在名次上會有差異。

##解題方法：
你點下 submit 之後會發現那個 id 並不是這題目的 id ，把 id 改掉，然後照著題目的要求寫出程式就可以過關。

##解題所需要的關鍵：
細心地看一下題號。

##解題程式碼：
```c
#include <cstdio>
int main() {
    char useless[1000];
    while(~scanf("%s", useless)) {
    printf("10361\n");
    }
    return 0;
}
```
