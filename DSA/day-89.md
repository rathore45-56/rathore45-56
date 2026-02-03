#include <bits/stdc++.h> 
int maximumProfit(vector<int> &prices){
   long long int min1=INT_MAX;
   long long int profit=0;
   for(long long int i: prices)
   {
       if(i<min1)
       min1=i;
       else
       profit=max(profit, i-min1);
   }

   return profit;
}
