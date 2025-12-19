Node <int>* find(Node  <int>*first, Node  <int>*second)
{
    if(first->next==NULL)
    {
        first->next=second;
        return first;
    }
    Node  <int>*prev=first;
    Node  <int>*curr=prev->next;
    Node  <int>*temp=second;
    while(curr!=NULL && temp!=NULL)
    {
        if((temp->data>=prev->data && temp->data<=curr->data))
        {
            prev->next=temp;
            Node  <int>*next_next=temp->next;
            temp->next=curr;
            prev=temp;
            temp=next_next;
        }
        else
        {
            prev=curr;
            curr=curr->next;
            if(curr==NULL)
            {
                prev->next=temp;
                return first;
            }
        }
    }
    return first;
}
Node<int>* sortTwoLists(Node<int>* first, Node<int>* second)
{
    if(first==NULL)
    return second;
    if(second==NULL)
    return first;
    if(first->data<=second->data)
    {
         return find(first,second);
    }
    else
    {
        return find(second,first);
    }

}
