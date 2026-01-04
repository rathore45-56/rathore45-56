#include <bits/stdc++.h> 
int findMinimumCost(string str) {
  stack<char>s;
  if(str.length()%2)
  return -1;
  for(int i=0;i<str.size();i++)
  {
    if(str[i]=='{')
    {
      s.push(str[i]);
    }
    else
    {
      if(!s.empty() && s.top()=='{')
      s.pop();
      else
      s.push(str[i]);
    }
  }
   int open=0,close=0;
   while(!s.empty())
   {
     if(s.top()=='{')
     {
     open++;
     s.pop();
     }
     else
     {
       close++;
       s.pop();
     }

   }
   open= (open+1)/2+(close+1)/2;
   return open;
}
