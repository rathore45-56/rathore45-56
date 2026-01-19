#include <bits/stdc++.h> 
int firstMissing(int arr[], int n)
{
    sort(arr,arr+n);
    int i=0,count=1;
    while(i<=n)
    {
        if(arr[i]>0)
        {
            if(arr[i]-count!=0)
            return count;
        i++;
        count++;
        }
        else
        {
            i++;
        }
    }
    return count;
}
