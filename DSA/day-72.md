class Solution {
  public:
    vector<int> firstNegInt(vector<int>& arr, int k) {
        deque<int>d;
        vector<int>v;
        for(int i=0;i<k;i++)
        {
        // In this i am finding firstnegative in window size k//.
            if(arr[i]<0)
            d.push_back(i);
        }
        if(d.empty())
       v.push_back(0);
        else
        v.push_back(arr[d.front()]);
        for(int i=k;i<arr.size();i++)
        {
         // in this i am finding next negative one by one but if in window size k there is already a negative exist
         // in deque then that negative will be printed first.
            if(!d.empty() && i-d.front()>=k)
            d.pop_front();
            if(arr[i]<0)
            {
                d.push_back(i);
            }
            if(d.empty())
            v.push_back(0);
            else
            v.push_back(arr[d.front()]);
        }
        return v;
    }
};
