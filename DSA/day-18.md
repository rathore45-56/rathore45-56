vector<int> countPrimes(int n)
{
    vector<int>a;
    int ans=0,flag=0;
    for(int i=2;i*i<=n;i++)
    {
        flag=0;
        while(n%i==0)
        {
            flag=1;
            ans=i;
            n=n/i;
        }
        if(flag==1)
        a.push_back(ans);
    }
    if(n>1)
    a.push_back(n);
    return a;
}
