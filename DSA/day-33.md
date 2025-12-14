Node* reverseDLL(Node* head)
{   
    Node *curr=head;
    Node *currnext=NULL;
     Node *prev=NULL;
    while(curr!=NULL)
    {
        currnext=curr->next;
        curr->next=prev;
        prev=curr;
        curr=currnext;
}
return prev;

}
