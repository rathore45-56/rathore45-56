#include <bits/stdc++.h> 
class Queue {
    int *arr;
int front1;
int rear;
int size;
public:
    Queue() {
        size=1000001;
       arr=new int[size];
       rear=0;
       front1=0;
    }
/*----------------- Public Functions of Queue -----------------*/
    bool isEmpty() {
        if(front1==rear)
        return 1;
        return 0;
    }
    void enqueue(int data) {
        if(rear==size)
        return;
       arr[rear++]=data;
    }
    int dequeue() {
        if(front1==rear)
        return -1;
        int ans=arr[front1];
        arr[front1]=-1;
        front1++;
        if(front1==rear)
        {
            front1=0;
            rear=0;
        }
        return ans;
    }
    int front() {
        if(front1==rear)
        return -1;
        return arr[front1];
    }
};
