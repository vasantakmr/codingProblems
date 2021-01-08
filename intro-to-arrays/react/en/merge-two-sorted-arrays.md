---
title: 'Merge 2 Sorted Arrays Without Extra Space Problem'
tocTitle: 'Merge Two Sorted Arrays'
description: ''
---


[Problem Link](https://practice.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1)

```clike
#include <bits/stdc++.h>
using namespace std;

void merge(int arr1[], int arr2[], int n, int m) 
{ 
    int rear, front, temp=0;
    front = 0;
    rear = n-1;
    while((arr1[rear]>arr2[front]) && (rear>=0) && (front<m)) {
        temp = arr1[rear];
        arr1[rear] = arr2[front];
        arr2[front] = temp;
        rear --;
        front++;
    }
    sort(arr1, arr1+n);
    sort(arr2, arr2+m);
}


int main()
{
   int n, m;
   cin>>n>>m;
   int arr1[n], arr2[m];
   for(int i=0; i<n; i++) {
       cin>>arr1[i];
   }
   for(int i=0; i<m; i++) {
       cin>>arr2[i];
   }
   merge(arr1, arr2, n, m);
   for(int i=0; i<n; i++) {
       cout<<arr1[i]<<" ";
   }
   for(int i=0; i<m; i++) {
       cout<<arr2[i]<<" ";
   }
   return 0;
}
```