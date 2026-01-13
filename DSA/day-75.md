Node* pairsSwap(Node *head)
{
    if(head==NULL || head->next==NULL)
    {
        return head;
    }
    Node *curr=head;;
    Node *currnext=curr->next;
    Node *temp=currnext->next;
    currnext->next=curr;
    curr->next=pairsSwap(temp);
    head=currnext;
    return head;
}
