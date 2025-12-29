<code/>
long long maxSubarraySum(vector<int> arr, int n)
{
    long long ans=0;
    long long max1=INT_MIN;
    for(int i=0;i<n;i++)
    {
        ans+=arr[i];
        if(ans<0)
        {
            ans=0;
        }
        max1=max(ans,max1);
    }
    return max1;
}
