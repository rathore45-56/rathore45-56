#include <bits/stdc++.h> 
int HCF(int x,int y)
{
  if(x==0)
  {
    return y;
  }

  int ans= HCF(y%x,x);
}
long long LCM(int x, int y)
{
  long x1=x,y1=y;
  int ans= HCF(x,y);
  long long ans1=x1*y1/ans;

  return ans1;

}
