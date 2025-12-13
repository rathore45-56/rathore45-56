<code/>
bool isCircular(Node* head){
   Node *temp=head;
   Node *curr=NULL;
   if(head==NULL)
   return 1;
   while(temp->next!=head)
   {
       if(temp->next==NULL)
       return 0;
       curr=temp;
       temp=temp->next;
       curr->next=NULL;
   }
   
  return 1;
}
