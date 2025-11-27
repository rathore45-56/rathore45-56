<code/>
class Solution {
    private:
    void calculatesubsets(vector<vector<int>>&b,vector<int>a,int i,vector<int>nums)
    {
        if(i>=nums.size())
        {
            b.push_back(a);
            return;
        }
        calculatesubsets(b,a,i+1,nums);
        a.push_back(nums[i]);
        calculatesubsets(b,a,i+1,nums);
}
public:
    vector<vector<int>> subsets(vector<int>& nums) {
       vector<vector<int>>b;
       vector<int>a;
       int i=0;
       calculatesubsets(b,a,i,nums);
       return b;
}
};
