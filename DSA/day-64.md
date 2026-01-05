class Solution {
  public:
    int celebrity(vector<vector<int>>& mat) {
        stack<int>s;
        for(int i=0;i<mat.size();i++)
        {
            s.push(i);
        }
        while(s.size()>1)
        {
            int a=s.top();
            s.pop();
            int b=s.top();
            s.pop();
            if(mat[a][b])
            {
                s.push(b);
            }
            else
            s.push(a);
        }
        int potentialcandidate=s.top();
        int count=0;
        for(int i=0;i<mat.size();i++)
        {
            if(mat[potentialcandidate][i]==0)
            count++;
        }
        if(count!=mat.size()-1)
        return -1;
        count=0;
        for(int i=0;i<mat.size();i++)
        {
            if(mat[i][potentialcandidate]==1)
            count++;
        }
        if(count!=mat.size())
        return -1;
        return potentialcandidate;
        }
};
