#include <bits/stdc++.h> 
int square(int a, int b, int m)
{
    // In this we are finding square of "A" till "B" times but with modulo "M" \\
    if(b==0)
    return 1;
    if(b==1)
    return a;
    int ans= square(a,b/2,m);
    if(b&1)
    {
        int k=(ans%m*ans%m)%m;
        ans= (a*k)%m;
    }
    else
    {
        ans=(ans%m*ans%m)%m;
    }
   return ans;


}
int solve(int a,int b,int c,int m){
    int ans= square(a,b,m);
    int value=0;
    for(int i=0;i<m;i++)
    {
        // Here we are looking for that multiple of "C" till "M" which when multiplies with "C" gives remainder "1" after taking modulo with "M". As GCD of C and M is given 1 \\
        if((c*i)%m==1){
            value=i;
            break;
            }
    }
    return (ans%m * value%m)%m;
    
}
