#include <bits/stdc++.h> 
bool areAnagram(string &str1, string &str2){
   vector<int>count1(26,0),count2(26,0);
   if(str1.size()>str2.size() || str2.size()>str1.size())
   return 0;

   for(int i=0;i<str1.size();i++)
   {
       int number=str1[i]-'a';
       count1[number]++;
   }
   for(int i=0;i<str2.size();i++)
   {
       int number=str2[i]-'a';
       count2[number]++;
   }
   if(count1!=count2)
   return 0;
            return 1;
}
