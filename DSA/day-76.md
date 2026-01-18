<code/>
#include <bits/stdc++.h> 
long long mergeto(vector<long long> &arr1, int i, int j)
{
    long long total=0;
    int mid=i+(j-i)/2;
    int len1=mid-i+1;
    int len2=j-mid;
    vector<long long> arr12(len1);
    vector<long long> arr13(len2);
    int idx1=0;
    int idx2=0,left=i;
    for(int k=0;k<len1;k++)
    {
        arr12[k]=arr1[i+k];
    }
    for(int h=0;h<len2;h++)
    {
        arr13[h]=arr1[mid+h+1];
    }
    while(idx1<len1 && idx2<len2)
    {
        if(arr12[idx1]<=arr13[idx2])
        {        
           arr1[left++]=arr12[idx1++];
        }
        else
        {
            arr1[left++]=arr13[idx2++];
        total+=(len1-idx1);
        }
    }
        while(idx1<len1)
        {
         arr1[left++]=arr12[idx1++];
        }
        while(idx2<len2)
        {
            arr1[left++]=arr13[idx2++];
        }
        return total;
}
long long mergeSort(vector<long long> &arr1, int i,int j)
{
       long long total=0;
    if(i>=j)
    return 0;
    int mid=i+(j-i)/2;
    long long L=mergeSort(arr1,i,mid);
    long long R=mergeSort(arr1,mid+1,j);
    long long current=mergeto(arr1,i,j);
    return L+R+current;
}
long long getInversions(long long *arr, int n){
    vector<long long>arr1;
       for(int i=0;i<n;i++)
       {
        arr1.push_back(arr[i]);
       }
    int right=arr1.size()-1;
   long long ans=mergeSort(arr1,0,right);
   return ans;
}
