class Solution {
    private:
    void create(Node *&head, Node* &tail, int digit)
    {
        Node *next1= new Node(digit);
        if(head==NULL)
        {
             head=next1;
             tail=next1;
             return;
        }
        tail->next=next1;
        tail=next1;
    }
  public:
    Node* cloneLinkedList(Node* head) {
        Node *temp=head;
        Node *anshead=NULL;
        Node *anstail=NULL;
        unordered_map<Node *, Node *>m;
        while(temp!=NULL)
        {
           create(anshead,anstail,temp->data);
           temp=temp->next;
        }
        temp=head;
        Node *newtemp=anshead;
        while(temp!=NULL)
        {
           m[temp]=newtemp;
           temp=temp->next;
           newtemp=newtemp->next;
        }
        temp=head;
        newtemp=anshead;
        while(temp!=NULL)
        {
            newtemp->random=m[temp->random];
            newtemp=newtemp->next;
            temp=temp->next;
        }
        return anshead;
        
    }
};
