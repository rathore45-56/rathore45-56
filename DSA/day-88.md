#include <bits/stdc++.h>

int lengthOfLongestConsecutiveSequence(vector<int> &arr, int n) {
// It takes O(nlogn) Time Complexity as i am sorting the array first//.
    sort(arr.begin(),arr.end());
    long long int max1=INT_MIN;
    long long int count=1;
    if(n==1)
    return 1;
    for(int i=0;i<n;i++)
    {
        if(arr[i]==arr[i+1])
        continue;
        else if(arr[i+1]-arr[i]==1)
        count++;
        else
        {
            max1=max(count,max1);
            count=1;
        }
    }
    if(count>max1)
    {
        return count;
    }
    return max1;
}
