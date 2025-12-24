<code/>
vector<int> getSecondOrderElements(int n, vector<int> a) {
      // Write your code here.
   int max = a[0], max2 = -1;
   int min = a[0], min2 = INT_MAX;
   for(int i=1;i<n;i++)
   {
       if(max<a[i])
       {
           max2 = max;
           max = a[i];
       }
       else if(max2<a[i])
           max2 = a[i];
       if(min>a[i])
       {
           min2= min;
           min = a[i];
       }
       else if(min2>a[i])
           min2 = a[i];
   }
   vector<int> ans;
   ans.push_back(max2);
   ans.push_back(min2);
   return ans;
}
