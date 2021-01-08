---
title: 'Count the Triplets Problem'
tocTitle: 'Count the Triplets'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/count-the-triplets/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int countTriplet(int arr[], int n)
{
    unordered_map<int, int> freq;
    int count =0, sum;
    for(int i=0; i<n; i++) {
        freq[arr[i]]++;
    }
    for(int i=0; i<n; i++) {
        for(int j=i+1; j<n; j++) {
            sum = arr[i]+arr[j];
            if(!(freq.find(sum)==freq.end())) {
                count = count+freq.at(sum);
            }
        }
    }
    return count;
}

int main() {
    int n;
    cin>>n;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    cout<<countTriplet(arr, n)<<endl;
}
```