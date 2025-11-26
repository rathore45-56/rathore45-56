<code/>
#include <bits/stdc++.h> 
const int mod=1e9+7;
int fiboSum(int n , int m)
{
	int arr[m];
	arr[0]=0;
	arr[1]=1;
	int sum=0;
	if(n<=1 && m>=1)
	{
		sum=1;
	}
	else if(n<=1 && m<1)
	sum =0;
	for(int i=2;i<=m;i++)
		{
			arr[i]=(arr[i-1]+arr[i-2])%mod;
			if(i>=n)
			{
				sum=(sum+arr[i])%mod;
			}
		}
	return sum;
}
