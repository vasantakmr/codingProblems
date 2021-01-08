---
title: 'Activity Selection Problem'
tocTitle: 'Activity Selection'
description: ''
commit: 4211d5e
---

[Problem Link](https://practice.geeksforgeeks.org/problems/activity-selection/0)

```clike
#include<bits/stdc++.h>
using namespace std;

struct Activity {
    int startT, endT;
};

int compar(Activity a1, Activity a2) {
    return a1.endT<a2.endT;
}

int activitySelection(int start[], int end[], int n){
    Activity arr[n];
    for(int i=0; i<n; i++) {
        arr[i].startT = start[i];
        arr[i].endT = end[i];
    }
    sort(arr, arr+n, compar);
    int i = 0, count = 1;
    for(int j=1; j<n; j++) {
        if(arr[i].endT<=arr[j].startT) {
            i = j;
            count++;
        }
    }
    return count;
}

int main() {
    int t;
    cin>>t;
    while(t--) {
        int n;
        cin>>n;
        int start[n], end[n];
        for(int i=0; i<n; i++) {
            cin>>start[i];
        }
        for(int i=0; i<n; i++) {
            cin>>end[i];
        }
        int ans;
        ans = activitySelection(start, end, n);
        cout<<ans<<endl;
    }
    return 0;
}