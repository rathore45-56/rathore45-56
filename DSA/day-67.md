#include <bits/stdc++.h>
class SpecialStack {
    stack<int>s;
    int min1;
    public:
    void push(int data) {
        // Implement the push() function.
         if(s.empty())
         min1=data;
         if(min1>data)
         {
             s.push(2*data-min1);
             min1=data;
         }
         else
         {
            s.push(data);
         }
         }
       void pop() {
       if(s.empty())
       return;
       if(s.top()>min1)
       s.pop();
       else
       {
       min1=2*min1-s.top();
       s.pop();
       }
    }
      int top() {
        // Implement the top() function.
       if(s.top()<min1)
       {
           return min1;
       }
       return s.top();
    }
       int getMin() {
        // Implement the getMin() function.
        return min1;
    }  
};
