<code/>
class Stack
{
    //Write your code here

public:
       Node *head=NULL;
       int size;
    Stack()
    {
        size=0;
    }
    int getSize()
    {
        return size;
    }
    bool isEmpty()
    {
        if(size==0)
        return true;
     return false;
    }
    void push(int data)
    {
        Node *next_next=new Node(data);
        next_next->next=head;
        head=next_next;
        size++;
    }
     void pop()
    {
        if(size==0)
        return ;
        Node *temp=head;
        head=head->next;
        delete temp;
        size--;
           }
    int getTop()
    {
        if(size==0)
        return -1;
     return head->data;
    }
};
