class Solution {
  public:
    string firstNonRepeating(string &s) {
       int arr[26]={0};
       queue<char>q;
       string ans="";
       for(int i=0;i<s.size();i++)
       { 
         // In this i am counting the alphabets and updating in Array 'arr' and the pushing element in queue as well//.
           arr[s[i]-'a']++;
           q.push(s[i]);
           while(!q.empty())
           {
           //In this i am popping element that occurs more than one time and putting one time occuring element in ans string //.
               if(arr[q.front()-'a']>1)
               q.pop();
               else
               {
               ans.push_back(q.front());
               break;
               }
           }
           // In this if statament i am putting '#' in ans string if queue gets empty//.
       if(q.empty())
       ans.push_back('#');
       }
       return ans;
        }
};
