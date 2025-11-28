int romanToInt(string s) {
    int i=0,j=1;
   unordered_map<char,int>m;
   int sum=0,sum1=0;
  m['I']=1,m['V']=5,m['X']=10,m['L']=50,m['C']=100,m['D']=500,m['M']=1000;
  while(i<j && j<s.size())
  {
        if(m[s[i]]<m[s[j]])
      {
          sum1-=m[s[i]];
          i++;
          j++;
      }
      else
      {
          char c=s[i];
          sum+=m[c];
          i++;
          j++;
          }
  }
  sum+=sum1;
  sum+=m[s[i]];
   
   return sum;
}
