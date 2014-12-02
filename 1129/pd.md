#10299 	PD - tsóng-thóng
##出題者：
Name: hydai

Mail: z54981220@gmail.com

##出題目的：
把題目拿去 Google 就可以知道那兩個字代表著台語的**總統**的發音

接著 Google 範例測資的兩個輸出，你會發現他們是歷任的美國總統，又透過那幾個數字，就可以知道輸入給的是屆數不是任數。

這題也是需要靈機一動的題目，不過我在放測資的時候沒有注意到有些總統的名字不固定，因此在有人反映之後才進行修正，把一些大家很容易不同步的測試資料拿掉。

##解題方法：
把人名跟屆數做好對應，讀入輸入後就直接輸出一行總統名字就會對了。

##解題所需要的關鍵：
Google 得知美國總統的屆數。

##解題程式碼：
```C
#include <stdio.h>
char nameList[][50] = {
"George Washington",
"George Washington",
"John Adams",
"Thomas Jefferson",
"Thomas Jefferson",
"James Madison",
"James Madison",
"James Monroe",
"James Monroe",
"John Quincy Adams",
"Andrew Jackson",
"Andrew Jackson",
"Martin Van Buren",
"William Henry Harrison",
"James Knox Polk",
"Zachary Taylor",
"Franklin Pierce",
"James Buchanan",
"Abraham Lincoln",
"Abraham Lincoln",
"Ulysses Grant",
"Ulysses Grant",
"Rutherford Birchard Hayes",
"James Garfield",
"Grover Cleveland",
"Benjamin Harrison",
"Grover Cleveland",
"William McKinley",
"William McKinley",
"Theodore Roosevelt",
"William Howard Taft",
"Woodrow Wilson",
"Woodrow Wilson",
"Warren Gamaliel Harding",
"Calvin Coolidge",
"Herbert Hoover",
"Franklin Delano Roosevelt",
"Franklin Delano Roosevelt",
"Franklin Delano Roosevelt",
"Franklin Delano Roosevelt",
"Harry S. Truman",
"Dwight Eisenhower",
"Dwight Eisenhower",
"John F. Kennedy",
"Lyndon Johnson",
"Richard Nixon",
"Richard Nixon",
"Jimmy Carter",
"Ronald Reagan",
"Ronald Reagan",
"George H. W. Bush",
"Bill Clinton",
"Bill Clinton",
"George W. Bush",
"George W. Bush",
"Barack Obama"
};
int main(int argc, char *argv[])
{
    int ind;
    while (~scanf("%d", &ind)) {
        printf("%s\n", nameList[ind-1]);
    }
    return 0;
}
```
