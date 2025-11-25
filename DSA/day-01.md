<code/>
#include <bits/stdc++.h> 
int flag=0;
void calculate(int a,int b,int c,int &x,int &y)
{
	if(a==0)
	{
		if(c%b==0)
		{
		x=0;
		y=c/b;
		return;
		}
		else
		{
			x=0;
			y=0;
			return;
		}
		}
	int i,j;
  calculate(b%a,a,c,i,j);
	x=j-(b/a)*i;
	y=i;
}
vector<int> linearEquation(int a, int b, int c)
{
	int x,y;
	calculate(a,b,c,x,y);
	if(x==0&&y==0)
	return {-1,-1};
	return {x,y};

}
