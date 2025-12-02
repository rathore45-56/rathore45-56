string lookAndSaySequence(int n) 
{
    if(n==1)
    return "1";
    if(n==2)
    return "11";
    string q="";
    string s="11";
    int count=0;
    for(int i=3;i<=n;i++)
    {
        count=1;
        q="";
          for(int j=1;j<=s.size();j++)
          {
              if(s[j]==s[j-1])
              {
                  count++;
              }
              else
              {
                 q+=to_string(count);
                 q+=s[j-1];
                 count=1;
                 }
          }
          s=q;
    }
        return q;
}
