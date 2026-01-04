#include <bits/stdc++.h> 
bool findRedundantBrackets(string &st)
{
    stack<char>s;
    bool redundant=true;
    for(int i=0;i<st.size();i++)
    {
        if(st[i]=='(' || st[i]=='+' || st[i]=='-' || st[i]=='/' || st[i]=='*')
        {
            s.push(st[i]);
        }
        else
        {
            redundant=true;
           if(st[i]==')')
           {
               while(s.top()!='(')
               {
                   char ch=s.top();
                 if(ch=='+' || ch=='-' || ch=='/' || ch=='*')  
                 redundant=false;
               s.pop();
               }
               if(redundant==true)
               return true;
               s.pop();
              }
    }
    }
    return false;
}
