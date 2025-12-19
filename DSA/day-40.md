#include <bits/stdc++.h> 
void sort012(int *arr, int n)
{
// In single scan //
   int c=0;
   for(int i=0;i<n;i++)
   {
      if(arr[i]==0)
      {
         swap(arr[i],arr[c]);
         c++;
      }
   }
   for(int i=c;i<n;i++)
   {
      if(arr[i]==1)
      {
         swap(arr[i],arr[c++]);
      }
   }
}
