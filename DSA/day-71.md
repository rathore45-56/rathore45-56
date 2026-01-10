#include <bits/stdc++.h> 
class Deque
{
    int *arr;
    int front;
    int rear;
    int size;
public:
    Deque(int n)
    {
       arr=new int[n];
       front=-1;
       rear=-1;
       size=n-1;
    }
    bool pushFront(int x)
    {
        if((front==0 && rear==size) || (front!=0 && rear==(front-1)%(size)))
        return false;
        if(front==-1)
        {
            front=rear=0;
        }
        else if(front==0 && rear!=size)
        {
            front=size;
        }
        else
        front--;
        arr[front]=x;
       return true;
    }
    bool pushRear(int x)
    {
        if((front==0 && rear==size) ||(front!=0 && rear==(front-1)%(size)))
        return false;
        if(front==-1)
        front=rear=0;
        else if(rear==size && front!=0)
        rear=0;
        else
        rear++;
        arr[rear]=x;
        return true;
        }
    int popFront()
    {
        if(front==-1)
        return -1;
        int ans=arr[front];
        arr[front]=-1;
       if(front==rear)
       front=rear=-1;
       else if(front==size)
       front=0;
       else
       front++;
       return ans;
    }
    int popRear()
    {
        if(front==-1)
        return -1;
        int ans=arr[rear];
        arr[rear]=-1;
        if(front==rear)
        front=rear=-1;
        else if(rear==0)
        {
            rear=size;
        }
        else
        rear--;
        return ans;
    }
    int getFront()
    {
        if(isEmpty())
        {
            return -1;
        }
        return arr[front];
    }
    int getRear()
    {
        if(isEmpty())
        {
            return -1;
        }
        return arr[rear];
    }
    bool isEmpty()
    {
        if(front==-1)
        return true;
       return false;
    }
    bool isFull()
    {
        if((front==0 && rear==size) || (front!=0 && rear==(front-1)%(size)))
        return true;
       return false;
    }
};
