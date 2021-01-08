---
title: 'Leaders in an array Problem'
tocTitle: 'Leaders in an array'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/leaders-in-an-array/0)

```clike
#include<bits/stdc++.h>
using namespace std;

vector<int> leaders(int arr[], int n){
    int maxEle = -1, temp;
    vector<int> vec;
    for(int i=0; i<n; i++) {
        if(arr[n-1-i]>=maxEle) {
            maxEle = arr[n-1-i];
            vec.push_back(maxEle);
        }
    }
    //reversing vector
    for(int i=0; i<(vec.size()/2); i++) {
        temp = vec[i];
        vec[i] = vec[vec.size()-1-i];
        vec[vec.size()-1-i] = temp;
    }
    return vec;
}

int main()
{
    int n;
    cin>>n;
    int arr[n];
    for(int i=0; i<n; i++) {
        cin>>arr[i];
    }
    vector<int> v = leaders(arr, n); 
    for(int i=0; i<v.size(); i++) {
        cout<<v[i]<<" ";
    }
   return 0;
}