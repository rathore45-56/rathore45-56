#include <bits/stdc++.h> 

int lengthOfLongestSubstring(string &s) {
   int n=s.size();
   if(n==1)
   return 1;

   string a="";
   string b="";
   for(int i=0;i<n;i++)
   {
      int j=0;
      while(j<a.size())
      {
         if(s[i]==a[j])
         {
         a=a.substr(j+1);
         break;}
         else
         j++;
      }
      a+=s[i];
      if(a.size()>b.size())
      b=a;
   }
   if(a==s)
   return a.size();
   return b.size();

}
