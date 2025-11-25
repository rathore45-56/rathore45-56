<code/>
class Solution {
public:
    vector<vector<int>> generate(int numrows) {
        if(numrows==0)
        return {};
        if(numrows==1)
        return {{1}};
        vector<vector<int>>b=generate(numrows-1);
        vector<int>x(numrows,1);
        for(int i=1;i<numrows-1;i++)
        {
            x[i]=b.back()[i-1]+b.back()[i];
        }
        b.push_back(x);
         return b;
        }
};
