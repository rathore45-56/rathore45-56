#include <bits/stdc++.h> 
int sumThreeStacks(vector<int>& A, vector<int>& B, vector<int>& C, 
					int lenA, int lenB, int lenC)
{
	int p=0,q=0,r=0;
	int sum1=0,sum2=0,sum3=0,ans=0;
  // In the below three loops i am finding a sum of seperate stacks.
	for(int i=0;i<lenA;i++)
	{
		sum1+=A[i];
	}
	for(int i=0;i<lenB;i++)
	{
		sum2+=B[i];
	}
	for(int i=0;i<lenC;i++)
	{
		sum3+=C[i];
	}
	while(p<lenA && q<lenB && r<lenC)
	{
  // In this loop i am finding a minimum of three stacks sum and trying to make other two stacks sums equal to that.
		ans=min(sum1,min(sum2,sum3));
		if(ans==sum1 && ans==sum2 && ans==sum3)
		return ans;
		if(ans<sum1)
        {	
		sum1-=A[p];
		p++;
		}
		if(ans<sum2)
		{
			sum2-=B[q];
		q++;
		}
		if(ans<sum3)
		{
			sum3-=C[r];
		    r++;
		}
	}
	return 0;
}
