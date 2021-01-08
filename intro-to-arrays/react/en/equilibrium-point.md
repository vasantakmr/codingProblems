---
title: 'Equilibrium Point Problem'
tocTitle: 'Equilibrium Point'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/equilibrium-point/0)

```clike
#include <bits/stdc++.h>
using namespace std;

int equilibriumPoint(long long arr[], int n) {
    if(n==1) {
        return 1;
    } else if(n==2) {
        return -1;
    }
    int sum = 0, curr_sum=0;
    for(int i=0; i<n; i++) {
        sum += arr[i]; 
    }
    for(int i=0; i<n-1; i++) {
        curr_sum = curr_sum + arr[i];
        if(curr_sum == (sum-arr[i+1]-curr_sum)) {
            return i+2;
        }
    }
    return -1;
}

int main()
{
    int n;
    cin>>n;
    long long int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    cout <<equilibriumPoint(arr, n)<< endl; 
    return 0;
}