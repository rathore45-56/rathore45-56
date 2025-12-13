  int getlen(Node *head)
  {
      int count=0;
      Node *temp=head;
      while(temp!=NULL)
      {
          count++;
       temp=temp->next;
      }
      return count;
  }
Node* kReverse(Node* head, int k) {
    int count=1;
    Node *curr=head;
    Node *currnext=NULL;
    Node *prev=NULL;
    int len= getlen(head);
    if(len<k)
    {
        return curr;
    }
    else
    {
    while(count<=k && curr!=NULL )
    {
       currnext=curr->next;
       curr->next=prev;
       prev=curr;
       curr=currnext;
       count++;
    }
    if(curr!=NULL)
    head->next= kReverse(curr, k);
     return prev;
    }
}
