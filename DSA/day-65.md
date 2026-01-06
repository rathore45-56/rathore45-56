class Solution {
    private:
    vector<int> solve1(vector<int>&arr, int a)
    {
        stack<int>s;
        vector<int>k(a);
        s.push(-1);
        for(int i=a-1;i>=0;i--)
        {
            while(s.top()!=-1 && arr[s.top()]>=arr[i])
            s.pop();
            k[i]=s.top();
            s.push(i);
        }
        return k;
    }
    private:
     vector<int> solve2(vector<int>&arr, int b)
    {
        stack<int>s;
        vector<int>l(b);
        s.push(-1);
        for(int i=0;i<b;i++)
        {
            while(s.top()!=-1 && arr[s.top()]>=arr[i])
            s.pop();
            l[i]=s.top();
            s.push(i);
         }
        return l;
    }
     private:
    int AreaofArray(vector<int>&arr, int n)
    {
        int max1=INT_MIN;
        vector<int>nextsmallest(n);
        vector<int>prevsmallest(n);
        nextsmallest=solve1(arr,n);
        prevsmallest=solve2(arr,n);
        for(int i=0;i<n;i++)
        {
            if(nextsmallest[i]==-1)
            {
                nextsmallest[i]=n;
            }
            int value=nextsmallest[i]-prevsmallest[i]-1;
            int area=value*arr[i];
            max1=max(max1,area);
        }
        return max1;
    }
  public:
    int maxArea(vector<vector<int>> &mat) {
    // In this  AreaofArray() function i am finding a area of intial row through largest rectangle in a histogram approach//
       int area= AreaofArray(mat[0], mat[0].size());
       for(int i=1;i<mat.size();i++)
       { // In this i am adding column of previous whose value is 1 and just add to the current so that  
            I can calculate an maximum area of combined rows through same largest rectangle in a histogram approach //
           for(int j=0;j<mat[0].size();j++)
           {
               if(mat[i][j]==1)
               mat[i][j]=mat[i][j]+mat[i-1][j];
               else
               mat[i][j]=0;
           }
           // In this i am keeping track of maximum area.
           area=max(area,AreaofArray(mat[i], mat[0].size()));
       }
        return area;
       }
};
