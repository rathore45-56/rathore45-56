class Solution {
public:
    vector<int> rearrangeArray(vector<int>& nums) {
        int n=nums.size()/2;
        vector<int>a;
        vector<int>b;
        vector<int>c;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]<0)
            {
                a.push_back(nums[i]);
            }
            else
            {
                b.push_back(nums[i]);
            }
        }
        int p=0;
        for(int i=0;i<a.size();i++)
        {
            c.push_back(b[i]);
            c.push_back(a[i]);
        }
      return c;
    }
};
