#10300 	PA - 凱薩與加解密法
##出題者：
Name: hydai

Mail: z54981220@gmail.com

##出題目的：
本題主要測試的是陣列運用以及字串處理的觀念。

##解題方法：
如果把字母 A-Z 換到 0-25 這個區間裡，只要透過取模數 mod 就可以很快速的算出結果。

key 雖然到很大，可以在我們轉換之後，可以直接對他取 mod 26 ，讓它變得很小，這樣就不會出現 overflow 的問題。

##解題所需要的關鍵：
Array, String

##解題程式碼：
```c
#include <stdio.h>
#include <string.h>
int main(int argc, char *argv[])
{
    char op[2];
    int key;
    char text[200];
    while (~scanf("%s%d%s", op, &key, text)) {
        key %= 26;
        if (op[0] == 'H') {
            char *ptr = text;
            while(*ptr) {
                *ptr = (*ptr-'A'+key)%26+'A';
                ptr++;
            }
        } else {
            char *ptr = text;
            while(*ptr) {
                *ptr = (*ptr-'A'-key+26)%26+'A';
                ptr++;
            }
        }
        printf("%s\n", text);
    }
    return 0;
}

```
