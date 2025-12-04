#include <bits/stdc++.h> 
vector<int> sumOfFactors(vector<int> &arr){
    int sum=1;
    vector<int>a;
    for(int i=0;i<arr.size();i++)
    {
        if(arr[i]==1)
        sum=0;
        else
        sum=1;
        sum=sum+arr[i];
    for(int j=2;j*j<=arr[i];j++)
    {
        if(arr[i]%j==0)
        {
            int value= arr[i]/j;
            if(j==value)
            sum+=arr[i]/j;
            else
            {
             sum+=arr[i]/j;
            sum+=j;
            }
        }
    }
    a.push_back(sum);
}
    return a;
}
