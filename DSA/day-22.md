#include <bits/stdc++.h> 
int findIndexOf(string a, string b){
	int j=0,ans=0,count=0;
	for(int i=0;i<b.length();i++)
	{
		if(b[i]==a[j])
		{
			if(count==0)
			ans=i;
			j++;
			count++;
				if(count==a.size())
				break;
		}
		else
		{
			ans=0;
			j=0;
			count=0;
		}
	}
	if(count==a.length())
	return ans;
	return -1;
}
