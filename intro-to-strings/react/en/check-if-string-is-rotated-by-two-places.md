---
title: 'Check if String is rotated by 2 places Problem'
tocTitle: 'Check if String is rotated by 2 places'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/check-if-string-is-rotated-by-two-places/0)

```clike
#include <bits/stdc++.h>
using namespace std;

bool isRotated(string str1, string str2)
{
    int len1, len2, r_flag = 1, l_flag = 1;
    len1 = str1.length();
    len2 = str2.length();
    if(len1!=len2)
        return false;
    for(int i=0; i<len1; i++) {
        if((str1[i]!=str2[(i+2)%len1])) {
            l_flag = 0;
        }
        if((str2[i]!=str1[(i+2)%len1])) {
            r_flag = 0;
        }
    }
    if(r_flag || l_flag) {
        return 1;
    }
    return 0;
}

int main()
{
   string s1, s2;
   cin>>s1>>s2;
   cout<<isRotated(s1,s2);
   return 0;
}
```