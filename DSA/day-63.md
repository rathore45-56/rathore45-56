<code/>
#include <stack>
#include <climits>
 
 vector<int> solve1(vector < int > & arr,int a)
 {
   /* In this function we are finding next smaller element from
   right side of given array
   But we are finding the indices of element and storing in vector<int> array k
   so that when we find the maximum area of a particular element then we can 
   just subtract the prev smaller element indices from that*/
    stack<int>s;
    vector<int>k(a);
    s.push(-1);
    for(int i=a-1;i>=0;i--)
    {
      while(s.top()!=-1 && arr[s.top()]>=arr[i])
      {
      s.pop();
      }
      k[i]=s.top();
      s.push(i);
    }
    return k;
 }
 vector<int> solve2(vector < int > & arr,int b)
 {
   /* In this function we are finding previous smaller element from
   left side of given array.
   But we are finding the indices of element and storing in vector<int> array k
   so that when we find the maximum area of a particular element then we can 
   just subtract the prev smaller element indices from next smaller element indices*/
   stack<int>s;
   vector<int>k(b);
   s.push(-1);
   for(int i=0;i<b;i++)
   {
     while(s.top()!=-1 && arr[s.top()]>=arr[i])
     {
       s.pop();
     }
     k[i]=s.top();
     s.push(i);
   }
   return k;
 }
 
 int largestRectangle(vector < int > & arr) {
   // This solution takes O(n) time complexity and O(n) space complexity.
   // Optimised approach.
    int n=arr.size();
   vector<int>nextsmallerelement(n);
   vector<int>prevsmallerelement(n);
   nextsmallerelement=solve1(arr, n);
   prevsmallerelement=solve2(arr, n);
 int area=0;
 int max1=INT_MIN;
   for(int i=0;i<n;i++)
   {
     if(nextsmallerelement[i]==-1)
     {
       /* Here we are putting nextsmaller value is equal to arr size because element after that is greater from it so it can make that area with that
       and then we are taking previous value and then mutliply it.*/
       nextsmallerelement[i]=n;
     }
     // Here i just multipy nextsmallerelement(value)-prevsmallerelement(value)-1 into array value;
     int value=nextsmallerelement[i]-prevsmallerelement[i]-1;
     area=value*arr[i];
     max1=max(max1,area);
   }

   return max1;
 }
