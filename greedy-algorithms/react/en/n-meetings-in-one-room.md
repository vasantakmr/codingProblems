---
title: 'N Meetings in One Room Problem'
tocTitle: 'N Meetings in One Room'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/n-meetings-in-one-room/0)

```clike
struct Activity {
    int startT;
    int endT;
    int arrPos;
};
int compar(Activity a1, Activity a2) {
    if (a1.endT < a2.endT) return true; 
    else if(a1.endT > a2.endT) return false; 
    else if(a1.arrPos < a2.arrPos) return true; 
    return false; 
}

void maxMeetings(int start[], int end[], int n) {
    Activity arr[n];
    for(int i=0; i<n; i++) {
        arr[i].startT = start[i];
        arr[i].endT = end[i];
        arr[i].arrPos = i+1;
    }
    sort(arr, arr+n, compar);
    int i = 0;
    cout<<arr[i].arrPos<<" ";
    for(int j=1; j<n; j++) {
        if(arr[i].endT<arr[j].startT) {
            i = j;
            cout<<arr[i].arrPos<<" ";
        }
    }
}
```