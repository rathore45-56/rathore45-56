#include<iostream>
#include<vector>
#include <bits/stdc++.h>
using namespace std;
int main() {
	int t;
	cin>>t;
	while(t--)
	{
	    int n;
	    cin>>n;
	    int arr[n];
	    for(int i=0;i<n;i++)
	    {
	        cin>>arr[i];
	    }
	    int flag=0;
	    for(int i=0;i<n-1;i++)
	    {
	        if(arr[i]>arr[i+1])
	        {
	        flag=1;
	        break;
	        }
	    }
	    int index=-1;
	    if(flag)
	    {
	        for(int i=0;i<n;i++)
	        {
	            if(arr[i]!=i+1)
	            index=i;
	        }
	          cout<<arr[index]<<endl;
	    }
	    else
	    cout<<"0"<<endl;
	}
	return 0;
}
