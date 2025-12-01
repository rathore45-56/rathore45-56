#include<bits/stdc++.h>

using namespace std;
void Generate(string s, int open, int close)
{
      if(open==0 && close==0)
      {
          cout<<s<<endl;
          return;
      }
      if(open==close)
      {
          string op1=s;
          op1.push_back('{');
         Generate(op1,open-1,close);
      }
      else if(open==0)
      {
          string op1=s;
          op1.push_back('}');
             Generate(op1,open,close-1);
      }
      else
      {
          string op1=s;
          string op2=s;
          op1.push_back('{');
          op2.push_back('}');
          Generate(op1,open-1,close);
          Generate(op2,open,close-1);
      }
}
void printParantheses(int n) {
    string s;
    Generate(s,n,n);
}
