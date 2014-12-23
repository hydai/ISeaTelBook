#10300 	PB - 教室排排坐
##出題者：
Name: hydai

Mail: z54981220@gmail.com

##出題目的：
本題主要要考的東西是觀察以及陣列的運用

##解題方法：
先觀察一下這個圖形，你會發現除了最後一排有四個以外，其他的都只有三個。

在觀察之後，我們可以對最後一排另外處理（也就是對人數小於 5 的）個別處理，之後的就可以推出一個公式來改裡頭的值了

##解題所需要的關鍵：
Array

##解題程式碼：
```c
#include <stdio.h>
int main(int argc, char *argv[])
{
    int T;
    while(~scanf("%d", &T)) {
        char classroom[6][30] = {
            "+-------------------------+",
            "|#.#.#.#.#.#.#.#.#.#.#...||",
            "|#.#.#.#.#.#.#.#.#.#.#...||",
            "|#.....................T.||",
            "|#.#.#.#.#.#.#.#.#.#.#...||",
            "+-------------------------+"
        };
        for (int i = 1; i <= T; i++) {
            if (i == 1) {
                classroom[1][1] = 'P';
            } else if (i == 2) {
                classroom[2][1] = 'P';
            } else if (i == 3) {
                classroom[3][1] = 'P';
            } else if (i == 4) {
                classroom[4][1] = 'P';
            } else {
                int tmp = i - 5;
                if (tmp % 3 == 2)
                    classroom[4][3 + (tmp / 3)*2] = 'P';
                else
                    classroom[1 + tmp % 3][3 + (tmp / 3)*2] = 'P';
            }
        }
        for (int i = 0; i < 6; i++) {
            puts(classroom[i]);
        }
        puts("");
    }
    return 0;
}

```
