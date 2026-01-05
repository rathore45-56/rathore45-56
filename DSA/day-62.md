#include <stack>
vector<int> nextSmallerElement(vector<int> &arr, int n)
{
    vector<int>a;
    vector<int>b;
    stack<int>s;
    s.push(-1);
    for(int i=arr.size()-1;i>=0;i--)
    {
        /* In while loop we are looking for smaller element that array element and when we find
        it we place it on the top of stack.*/
        while(s.top()>=arr[i])
        {
            s.pop();
        }
        int ans=s.top();
        s.push(arr[i]);
        a.push_back(ans);
  }
    for(int i=a.size()-1;i>=0;i--)
    {
        b.push_back(a[i]);
    }
    return b;
}
