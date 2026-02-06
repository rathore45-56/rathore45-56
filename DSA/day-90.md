#include <bits/stdc++.h>

string fourSum(vector<int> arr, int target, int n) {
  
  sort(arr.begin(),arr.end());
  for(int i=0;i<n;i++)
  {
      for(int j=i+1;j<n;j++)
      {
          int q=j+1;
          int e=n-1;
          int sum=target-(arr[i]+arr[j]);
          while(q<e)
          {
              if(arr[q]+arr[e]>sum)
              e--;
              else if(arr[q]+arr[e]==sum)
              return "Yes";
              else
              q++;
          }
      }

  }
  return "No";
}
