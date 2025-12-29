class Solution {
public:
    string removeOuterParentheses(string s) {
        string str="";
        string str1="";
        string finalstr="";
        int k=0;
        int open=0;
        int close=0;
        for(int i=0;i<s.size();i++)
        {
           if(s[i]=='(')
           {
            open++;
            str+=s[i];
           }
           else
           {
            close++;
            str+=s[i];
           }
           if(open==close)
           {
            for(int i=0;i<str.size();i++)
            {
                if(i==0 || i==str.size()-1)
                {
                    continue;
                }
                else
                {
                    str1+=str[i];
                }
            }
            finalstr+=str1;
            str="";
            str1="";
            open=0;
            close=0;
           }
}
        return finalstr;
    }
};
