bool areIsomorphic(string &str1, string &str2)
{
    int count=0;
    vector<int> count1(26, 0);
   vector<int> count2(26, 0);
    int size = str1.size();
    if(str1.size() != str2.size()) {
     return 0;
     }
     for(int i=0; i<size; i++) {
       int number1=str1[i]-'a';
       int number2=str2[i]-'a';
       if(str1Index[number1]!=str2Index[number2])
       return 0;
       str1Index[number1]++;
       str2Index[number2]++;
 }
 return 1;

}
