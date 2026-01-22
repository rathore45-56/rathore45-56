#include<iostream>
#include<vector>
#include <bits/stdc++.h>
using namespace std;
int main() {
	int t;
	cin>>t;
    while(t--)
    {
        int N,M;
        cin>>N>>M;
        int arr1[N],arr2[M];
        for(int i=0;i<N;i++)
        {
            cin>>arr1[i];
        }
         for(int i=0;i<M;i++)
        {
            cin>>arr2[i];
        }
        sort(arr1,arr1+N);
        sort(arr2,arr2+M);
        int count=0;
        int index1=0,index2=0;
        while(index1<N && index2<M)
        {
            if(arr1[index1]>arr2[index2])
            {
                count+=N-index1;
                index2++;
            }
            else
            {
                index1++;
            }
        }
        cout<<count<<endl;
    }
	return 0;
}
