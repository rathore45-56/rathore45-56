#include <bits/stdc++.h>

vector<int> majorityElementII(vector<int> &arr)
{
   int count=1;
   int n=arr.size();
   vector<int>ans2;
   sort(arr.begin(),arr.end());
   int p=arr[n-1];
   vector<int>ans1(p+1,0);

   for(int i=0;i<arr.size()-1;i++)
   {
       if(arr[i]!=arr[i+1])
       {
           ans1[arr[i]]=count;
       count=1;
       }
       else
       {
           count++;
       }
   }
   if(count>0)
   {
      ans1[arr[n-1]]=count;
   }

   for(int i=0;i<ans1.size();i++)
   {
       int k=n/3;
       if(ans1[i]>k)
       ans2.push_back(i);
   }
   return ans2;

}
