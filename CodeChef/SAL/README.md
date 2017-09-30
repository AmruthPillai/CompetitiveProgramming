# Alternative String
**Problem Code:** SAL  
**Problem Link:** https://www.codechef.com/CSEP2017/problems/SAL

## Problem Description
A String always consists of two distinct alternating characters. For example, if string 's two distinct characters are x and y, then it could be xyxyx or yxyxy but not xxyy or xyyx. You can convert some string to the string format specified above by deleting characters from the string. When you delete a character from the string, you must delete all occurrences of it in the string. For example, if the string is abaacdabd and you delete the character a, then the string becomes bcdbd. Given the string, convert it to the longest possible string which meets the specifications given in the first paragraph. Then print the length of string on a new line; if no string can be formed from the given string, print 0 instead.  

## Input
The first line of the input contains an integer T denoting the number of test cases.The subsequent test cases each contained in two lines have an integer N detailing the number of characters in the string and the next line has the string.

## Output
Print the maximum length of the string which also adheres to the rules as given. If it is not possible to form such a string, print 0.

## Example
```
Input:
1
4
beab

Output:
3
```

## Explanation
In beab, we deleted an e and got 'bab' thus forming an alternating string, whose length was 3.

## Code (C++)
```
#include <iostream>
#include <string>
using namespace std;

int slength(const string& text, char x, char y) {
    char last_seen = 0;
    int length = 0;
    for (char ch : text) {
        if (ch != x && ch != y) continue;
        if (last_seen == ch) return 0;
        last_seen = ch;
        length += 1;
    }
    return length >= 2 ? length : 0;
}

int main() {
    int t; cin >> t;

    for (int i = 0; i < t; i++) {
        int n; cin >> n;
        string text; cin >> text;
        int max_slength = 0;
        for (char x = 'a'; x <= 'z'; ++x) {
            for (char y = x + 1; y <= 'z'; ++y) {
                max_slength = max(max_slength, slength(text, x, y));
            }
        }
        cout << max_slength << endl;
    }
    return 0;
}
```
