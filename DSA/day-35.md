Node *removeLoop(Node *head)
{
    map<Node *, bool>m;
    Node *temp=head;
    Node *tail=head;
    while(temp!=NULL)
    {
        if(m[temp])
        {
        tail->next=NULL;
        break;
        }
        m[temp]=true;
        tail=temp;
        temp=temp->next;
        }
    return head;
}
