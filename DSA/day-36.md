
Node * removeDuplicates(Node *head)
{
      Node *temp=head;
     while(temp!=NULL && temp->next!=NULL)
    {
        Node *Nextnode=temp->next;
        while(Nextnode!=NULL && Nextnode->data==temp->data)
        {
            Node*useless=Nextnode;
            Nextnode=Nextnode->next;
            delete(useless);
        }
        temp->next=Nextnode;
        if(Nextnode!=NULL)
        Nextnode->prev=temp;
        temp=temp->next;
    }
    return head;
}
