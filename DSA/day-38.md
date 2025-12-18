Node* sortList(Node *head){
    int Numberofzeroes=0;
    int Numberofones=0;
    int Numberoftwos=0;
    Node *c=head;
    while(c!=NULL)
    {
        if(c->data==0)
        {
           Numberofzeroes++;
        }
        else if(c->data==1)
        {
            Numberofones++;
        }
        else
        {
            Numberoftwos++;
        }
        c=c->next;
    }
    Node *temp=head;;
    while(temp!=NULL)
    {
        if(Numberofzeroes)
        {
            temp->data=0;
            Numberofzeroes--;
            }
        else if(Numberofones)
        {
            temp->data=1;
            Numberofones--;
        }
        else{
            temp->data=2;
            Numberoftwos--;
        }
        temp=temp->next;
    }
    return head;
}
