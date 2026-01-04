#include <bits/stdc++.h> 
void solve(stack<int> &s,int num)
{
	if(s.empty())
	{
		s.push(num);
		return;
	}
	int num2=s.top();
	if(num2>num)
	{
	s.pop();
	solve(s, num);
	s.push(num2);
	}
    else
	{
	s.push(num);
	return;
	}
	 
}
void sortStack(stack<int> &stack)
{
	if(stack.empty())
	return;
  int num=stack.top();
	stack.pop();
	sortStack(stack);
	solve(stack,num);

}
