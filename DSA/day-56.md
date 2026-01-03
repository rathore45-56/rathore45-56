bool isValidParenthesis(string st)
{
    stack<char>s;
    for(int i=0;i<st.size();i++)
    {
        if(st[i]=='{' || st[i]=='(' || st[i]=='[')
        {
            s.push(st[i]);
        }
        else
        {
            if(st[i]=='}')
            {
                if(s.empty() || s.top()!='{')
                return false;
                else
                s.pop();
            }
            else if(st[i]==')')
            {
                 if(s.empty() || s.top()!='(')
                return false;
                else
                s.pop();
            }
            else
            {
                if( s.empty() || s.top()!='[')
                return false;
                else
                s.pop();
            }
       }
    }
    return true;
}
