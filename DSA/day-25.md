#include <bits/stdc++.h> 
int findTwoGroups(int n) {
	int sum=0;
	for(int i=1;i<=n;i++)
	{
		sum+=i;
	}
	if(sum%2)
	return 1;
   
   return 0;
}
