<code/>
#include <vector>
#include <string>
using namespace std;
vector<int> findAnagramsIndices(string str, string ptr, int n, int m){
    vector<int>a;
   int k=0;
   vector<int>count1(26,0);
   vector<int>count2(26,0);
   for(int i=0;i<m;i++)
   {
       char temp=ptr[i];
       int number= temp-'A';
       count1[number]++;
   }
   while(k<=n-m)
   {
       for(int j=k;j<m+k;j++)
       {
           char temp=str[j];
           int number=temp-'A';
           count2[number]++;
       }
       if(count1==count2)
       {
           a.push_back(k);
       }
       for(int i=0;i<26;i++)
       {
           count2[i]=0;
       }
       k++;
   }
   return a;
}
