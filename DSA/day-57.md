#include <bits/stdc++.h> 
stack<int> solve(stack<int>& mystack, int x, int size1)
{
    if(size1==0)
    {
        mystack.push(x);
        return mystack;
    }
    int num=mystack.top();
    mystack.pop();
    solve(mystack,x,size1-1);
    mystack.push(num);
    return mystack;
}
stack<int> pushAtBottom(stack<int>& mystack, int x) 
{
    int size1=mystack.size();
    solve(mystack,x,size1);
    return mystack;
}
