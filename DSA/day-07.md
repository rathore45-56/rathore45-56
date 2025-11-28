<code/>
class Solution {
    private:
    void calculatecombinations(string op, int index,string arr[],vector<string>&a,string digits)
    {
         if(index>=digits.size())
         {
          a.push_back(op);
          return;
         }
         int i= digits[index]-'0';
         string value= arr[i];
         for(int i=0;i<value.length();i++)
         {
            op.push_back(value[i]);
            calculatecombinations(op, index+1 ,arr,a,digits);
            op.pop_back();
         }
          }
public:
    vector<string> letterCombinations(string digits) {
        vector<string>a;
        string op;
        int index=0;
        string arr[10]={"","","abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"};
        calculatecombinations(op, index,arr,a,digits);
        return a;
    }
};
