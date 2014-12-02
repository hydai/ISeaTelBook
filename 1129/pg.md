#10303 	PG - Submit the Code
##出題者：
Name: henry

Mail: henryyang42@gmail.com

##出題目的&解題方法：
本題是跟網頁比較相關的題目，我們把正確答案直接印在網頁上，你可以捲動畫面，但是任何的點擊都會直接引導到登出畫面。（我們在程式碼開頭有特別提醒，**DO NOT TOUCH ANYTHING**）

解題有好幾種方式，你可以直接把那個程式碼打過一遍送上去就會過；也可以打開網頁原始碼，複製出來；或者把你的 `javascript` 關掉就可以點擊＆複製頁面的程式碼。

##解題所需要的關鍵：
網頁原始碼，或是 `javascript` 相關的知識。

##解題程式碼：
```CPP
/*
 *
 * Don't touch anything!!!
 *
 */
#include <cstdio>
#include <iostream>
#include <string>
#include <sstream>
#include <cstring>
#include <vector>
using namespace std;
int tile_ct[34], valid, tmp[34], kase;
vector<int> ans;
string tiles[] = {
    "1T", "2T", "3T", "4T", "5T", "6T", "7T", "8T", "9T",
    "1S", "2S", "3S", "4S", "5S", "6S", "7S", "8S", "9S",
    "1W", "2W", "3W", "4W", "5W", "6W", "7W", "8W", "9W",
    "DONG", "NAN", "XI", "BEI", "ZHONG", "FA", "BAI"
};
int to_int(string &tile) {
    for (int i = 0; i < 34; i++)
        if (tile == tiles[i])
            return i;
}
void dfs(int lv) {
    if (lv == 5 || valid) {
        valid = 1;
        return;
    }
    if (lv == 0) {
        for (int i = 0; i < 34; i++) {
            if (tmp[i] >= 2) {
                tmp[i] -= 2;
                dfs(lv + 1);
                tmp[i] += 2;
            }
        }
    }
    else {
        for (int i = 0; i < 34; i++) {
            if (tmp[i] >= 3) {
                tmp[i] -= 3;
                dfs(lv + 1);
                tmp[i] += 3;
            }
            if (i < 27 && i / 9 == (i + 2) / 9 && tmp[i] && tmp[i + 1] && tmp[i + 2]) {
                tmp[i]--, tmp[i + 1]--, tmp[i + 2]--;
                dfs(lv + 1);
                tmp[i]++, tmp[i + 1]++, tmp[i + 2]++;
            }
        }
    }
}
int main() {
    string tok, str;
    while (getline(cin, str)) {
        if (str == "0")
            break;
        memset(tile_ct, 0, sizeof(tile_ct));
        ans.clear();
        stringstream ss(str);
        while (ss >> tok)
            tile_ct[to_int(tok)]++;
        for (int i = 0; i < 34; i++)
            if (tile_ct[i] < 4) {
                valid = 0;
                memcpy(tmp, tile_ct, sizeof(tile_ct));
                tmp[i]++;
                dfs(0);
                if (valid)
                    ans.push_back(i);
            }
        printf("Case %d: ", ++kase);
        if (ans.size() == 0)
            puts("Not ready");
        else {
            for (int i = 0; i < ans.size(); i++)
                cout << (i ? " " : "") << tiles[ans[i]];
            puts("");
        }
    }
    return 0;
}
```
