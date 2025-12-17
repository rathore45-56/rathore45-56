Node *removeDuplicates(Node *head)
{
    Node *prev=head;
    Node *curr=head;
    unordered_map<int,bool>m;
    while(curr!=NULL)
    {
        if(!m[curr->data])
        {
         m[curr->data]=true;
         prev=curr;
         curr=curr->next;
        }
        else
        {
           Node *Nextnode=curr->next;
           delete(curr);
           prev->next=Nextnode;
           curr=Nextnode;
        }
    }
    return head;
}
