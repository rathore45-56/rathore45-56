#include<iostream>
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
    sort(arr,arr+n);
int count=1;
  int ans=arr[0];
  int p=0;
    for(int i=1;i<n;i++)
    {
        if(arr[i]!=arr[i-1])
        {
            if(count>p)
            {
                p=count;
                ans=arr[i-1];
            }
            count=1;
        }
        else
        {
            count++;
        }
    }
    if(count>p)
    {
       ans=arr[n-1];
    }
    cout<<ans<<endl;
}
return 0;	
}
