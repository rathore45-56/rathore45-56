#include <bits/stdc++.h> 
void find(string s, vector<string>&a, int n,int index)
{
    if(index>=n)
    {
        a.push_back(s);
        return;
    }
    for(int j=index;j<n;j++)
    {
        swap(s[index],s[j]);
        find(s,a,n,index+1);
        swap(s[index],s[j]);
    }
}
vector<string> findPermutations(string &s) {
    vector<string>a;
    int n= s.size();
    int index=0;
    find(s,a,n,index);
    return a;
}
