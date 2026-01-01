// Stack class.
class Stack {
    
public:
        int *arr;
        int top1;
        int size;
    Stack(int capacity) {
       this->size=capacity;
       arr=new int[size];
       top1=-1;
    }
      void push(int num) {
        if(size-top1>1)
        {
            arr[++top1]=num;
        }
    }
    int pop() {
       if(top1>=0)
       {
           int ans=arr[top1];
           top1--;
           return ans;
       }
       return -1;
    }
    int top() {
        if(top1>=0)
        return arr[top1];
        return -1;
    }
    int isEmpty() {
        if(top1==-1)
        return 1;
     return 0;
    }
    int isFull() {
        if(size-top1==1)
        return 1;
      return 0;
    }
    
};
