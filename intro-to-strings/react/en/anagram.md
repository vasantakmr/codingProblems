---
title: 'Anagram Problem'
tocTitle: 'Anagram'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/anagram-1587115620/1)

```clike
#include <bits/stdc++.h>
using namespace std;

bool isAnagram(string a, string b){
    int arr[26] = { 0 };
    for(int i=0; i<a.length(); i++) {
        arr[a[i]-'a']++;
    }
    for(int i=0; i<b.length(); i++) {
        arr[b[i]-'a']--;
    }
    for(int i=0; i<26; i++) {
        if(arr[i]!=0) {
            return 0;
        }
    }
    return 1;
}

int main()
{
   string s1, s2;
   cin>>s1>>s2;
   cout<<isAnagram(s1,s2);
   return 0;
}
```