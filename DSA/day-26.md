#include <vector>
string multiplyStrings(string a , string b ){
    int n=a.size();
    int m=b.size();
     vector<int>k(n+m,0);
     for(int i=n-1;i>=0;i--)
     {
       for(int j=m-1;j>=0;j--)
       {
         int number1= a[i]-'0';
         int number2=b[j]-'0';
          int product= number1*number2;
           int sum= product+k[i+j+1];
           int p= sum%10;
           int q= sum/10;
           k[i+j+1]=p;
           k[i+j]=k[i+j]+q;
       }
     }
     string str="";
     for(auto i: k)
     {
       if(str.size()==0 && i==0)
       continue;
       str+=to_string(i);;
     }
     if(str.size()==0)
     return "0";
      return str;
}
