<Code/>
#include <bits/stdc++.h> 
int compareVersions(string a, string b) 
{
   int i=0,j=0;
   long q,p;
   int n1=a.size(),n2=b.size();
   while(i<n1 || j<n2)
   {
       q=0;
       p=0;
         while(i<n1 && a[i]!='.')
         {
             int number=a[i]-'0';
             q=q*10+number;
             i++;
         }
          while(j<n2 && b[j]!='.')
         {
             int number=b[j]-'0';
             p=p*10+number;
             j++;
         }
         if(q>p)
         return 1;
         else if(p>q)
         return -1;
         i++;
         j++;

   }
   return 0;
}
