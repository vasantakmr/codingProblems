---
title: 'Flood Fill Algorithm'
tocTitle: 'Flood Fill Algorithm'
description: ''
---

[Problem Link](https://practice.geeksforgeeks.org/problems/flood-fill-algorithm/0)

```clike
#include<bits/stdc++.h>
using namespace std;

void floodFill(vector<vector<int>> &matx, int x, int y, int old, int k, int n, int m) {
    if ( x<0 || y<0 || x>=n || y>=m || matx[x][y]!=old) {
        return;
    }
    matx[x][y] = k;
    floodFill(matx, x-1, y, old, k, n, m);
    floodFill(matx, x+1, y, old, k, n, m);
    floodFill(matx, x, y-1, old, k, n, m);
    floodFill(matx, x, y+1, old, k, n, m);
}

int main() {
	int t;
	cin>>t;
	while(t--) {
	    int n, m, x, y, k, old_colour;
	    cin>>n>>m;
	    vector<vector<int>> matx( n , vector<int> (m, 0));
	    for(int i=0; i<n; i++) {
	        for(int j=0; j<m; j++) {
	            cin>>matx[i][j];
	        }
	    }
	    cin>>x>>y>>k;
	    old_colour = matx[x][y];
	    floodFill(matx, x, y, old_colour, k, n, m);
	    for(int i=0; i<n; i++) {
	        for(int j=0; j<m; j++) {
	            cout<<matx[i][j]<<" ";
	        }
	    }
	    cout<<endl;
	}
	return 0; 
}