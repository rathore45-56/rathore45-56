#include <bits/stdc++.h> 
bool findPattern(string p, string s)
{
    int i=0;
    int n=s.length();
    int m=p.length();
    string op="";
    while(i<=n-m)
    {
         for(int j=i;j<m+i;j++)
         {
            op.push_back(s[j]);
         }
         if(p==op)
         {
         return 1;
         }
         op="";
         i++;
    }
    return 0;
}
