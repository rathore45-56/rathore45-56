void solve(Node *curr, Node *currnext, Node *prev, Node *&head)
{
    if(curr==NULL)
    {
        head=prev;
    return;
    }
    currnext=curr->next;
    curr->next=prev;
    solve(currnext, currnext, curr,head);

}
Node* reverseLinkedList(Node *head)
{
   Node *prev=NULL;
   Node *curr=head;
   Node *currnext=head;

  solve(curr,currnext,prev,head);
   return head;
}
