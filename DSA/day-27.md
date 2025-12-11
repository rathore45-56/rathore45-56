<code/>
bool checkMember(int n){
  int a=0,b=1,c=0;
  if(n==0 || n==1)
  return  true;
  for(int i=2;i<=n+1;i++)
  {
     c=a+b;
     if(c==n)
     {
       return true;
       break;
     }
     a=b;
     b=c;
  }
 return false;
}
