void insertatbottom(stack<int> &s,int num)
{
    if(s.size()==0)
    {
       //Here we are putting top element at bottom
       s.push(num);
       return;
    }
     int num2=s.top();
     s.pop();
    insertatbottom(s,num);
    /* In this we are putting element one by one after putting
    element at bottom*/
    s.push(num2);
}
void reverseStack(stack<int> &s) {
   if(s.size()==0)
   return;

   int num=s.top();
   s.pop();
   // This reverseStack function pop all elements first
   reverseStack(s);
   /* Then insertatbottom puts the top element at bottom same as insert element at bottom 
   question*/
   insertatbottom(s,num);
   
}
