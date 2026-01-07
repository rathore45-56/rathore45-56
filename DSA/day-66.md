#include <bits/stdc++.h> 
class NStack
{
     int *arr;
   int *top;
   int *next;
   int freespot;
   int n,p;
public:
    // Initialize your data structure.
    NStack(int N, int S)
    {
        // Write your code here.
        n=N;
        p=S;
        arr=new int[p];
        top=new int[n];
        next=new int[p];
        for(int i=0;i<n;i++)
        {
            top[i]=-1;
        }
        for(int i=0;i<p;i++)
        {
            next[i]=i+1;
        }
        next[p-1]=-1;
        freespot=0;
        }
     // Pushes 'X' into the Mth stack. Returns true if it gets pushed into the stack, and false otherwise.
    bool push(int x, int m)
    {
        if(freespot==-1)
        return false;
        // Here i am finding freeindex from next array which is to next available space //
        int index=freespot;
        // Then i am looking for next available space//
        freespot=next[index];
        // In this i am putting value on that particular index//
        arr[index]=x;
        // Here i am keeping track of particular stack //
        next[index]=top[m-1];
        // In this i am updating top of the particular stack //
        top[m-1]=index;  
        return true;
          }
     // Pops top element from Mth Stack. Returns -1 if the stack is empty, otherwise returns the popped element.
    int pop(int m)
    {
    // In this i am doing just opposite of push//
        if(top[m-1]==-1)
        return -1;
       int index=top[m-1];
       top[m-1]=next[index];
       next[index]=freespot;
       freespot=index;
        return arr[index];
    }
};
