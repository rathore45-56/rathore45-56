<code/>
int findLargestMinDistance(vector<int> &arr, int k)
{
   long long int sum=0;
   int n=arr.size();
   for(int i=0;i<n;i++)
   {
       sum+=arr[i];
   }
   long long int s=0,e=sum;
   long long int sum1=0,count=1,ans=-1;
 
   while(s<=e)
   {
       sum1=0;
       count=1;
       int c=0;
       int mid=s+(e-s)/2;
       for(int i=0;i<n;i++)
       {
           if(sum1+arr[i]<=mid)
           {
               sum1+=arr[i];
           }
           else
           {
               count++;
               if(count>k || arr[i]>mid)
               {
               c=1;
               break;
               }
               sum1=arr[i];
           }
       }
       if(c==1)
       {
           s=mid+1;
       }
       else
       {
           ans=mid;
         e=mid-1;
       }
   }
   return ans;
}
