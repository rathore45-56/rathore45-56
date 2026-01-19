#include <bits/stdc++.h> 
long long ayushGivesNinjatest(int n, int m, vector<int> time) 
{	long long sum=0;
int c;
long long int count=0;
long long int ans=0;
long long int sum1;
	for(int i=0;i<m;i++)
	{
		sum+=time[i];
	}
	long long i=0,j=sum;
	while(i<=j)
	{
		c=0;
		sum1=0;
		count=0;
		long long mid=i+(j-i)/2;
		for(int k=0;k<m;k++)
		{
			if(sum1+time[k]<=mid)
			{
			sum1+=time[k];
			}
			else
			{
				count++;
				if(count>=n || time[k]>mid)
				{
				c=1;
				break;
				}
			   sum1=time[k];
			}
		}
		if(c==0)
		{
		ans=mid;
		j=mid-1;
		}
		else
		{
			i=mid+1;
		}
	}
	return ans;
}
