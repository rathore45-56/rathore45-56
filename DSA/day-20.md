#include <bits/stdc++.h> 
int sumFourDivisors(vector<int> &arr, int n)
{
    int count=2,sum=0,flag=0,sum1=0;
    for(int i=0;i<n;i++)
    {
        sum=0;
        count=2;
        int value=arr[i];
        if(value==1)
        sum=0;
        else
        sum=1;
        sum+=value;
        for(int j=2;j*j<=value;j++)
        {
            if(value%j==0)
            {
            int divisor= arr[i]/j;
            if(j==divisor)
            {
                count++;
                sum+=j;
            }
            else
         {
             count+=2;
             sum+=divisor;
             sum+=j;
         }
            }
        }
            if(count==4)
            {
                sum1+=sum;
            }
      }
    return sum1;
}
