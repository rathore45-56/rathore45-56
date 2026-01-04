#include <bits/stdc++.h> 
int findMinimumCost(string str) {
  stack<char>s;
  if(str.length()%2)
  // Here we are returning -1 for odd length of string because valid strings can be possible for even length only.
  return -1;
  for(int i=0;i<str.size();i++)
  {
  // In this loop we are trying for finding invalid expressions like:>
  // 1-> {{{{{{{.....
  // 2-> }}}}}}}}}}....
  // 3->}}}}{{{{{.....
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
   // In this we are counting open and close brackets.
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
   // Here we are applying formula for all of the invalid cases that i have mentioned above as 1,2,3.
   open= (open+1)/2+(close+1)/2;
   return open;
}
