void eradicate(int mid, Node* &tail)
{
    int count=1;
     while(count<mid)
     {
         tail=tail->next;
         count++;
     }
    
}
int findlen(Node *head)
{
    Node *temp=head;
    int count=0;
    while(temp!=NULL)
    {
        count++;
        temp=temp->next;
    }
    return count;
}

Node *findMiddle(Node *head) {
      int len= findlen(head);
      int mid= len/2+1;
      Node *tail=head;
     eradicate(mid,tail);
     return tail;
}
