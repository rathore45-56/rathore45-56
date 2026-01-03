#include <bits/stdc++.h> 
void deleteMiddle(stack<int>&s, int N){
   if(N==0)
   s.pop();
   else
   {
   vector<int>a;
         int value=(N)/2;
         int count=0;
         for(int i=0;i<N;i++)
         {
            if(count!=value)
            {
            int num=s.top();
            s.pop();
            count++;
            a.push_back(num);
            }
            else
            {
            s.pop();
            break;
            }
         }
        for(int i=a.size()-1;i>=0;i--)
         {
            s.push(a[i]);
         }
   }
     
   
}
