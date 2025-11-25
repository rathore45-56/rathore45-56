<code/>
#include <bits/stdc++.h> 
long long sum=0;
long long evenSumTillN(int n) {
    if(n==0)
    return 0;
    if(n&1)
    {
        evenSumTillN(n-1);
    }
    else
    { 
      sum=n+ evenSumTillN(n-2);
      return sum;
    }
}
