<code 1/> Used map method
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


Another method:-
<code 
/> Used floyd's detection method
Node *removeLoop(Node *head)
{
    Node *slow=head;
    Node *fast=head;
    Node *intersection=NULL;
    while(slow!=NULL && fast!=NULL)
    {
        // In this we are looking for loop detection through floyd's detection method by maintaining two pointers fast
        // and slow;
        fast=fast->next;
        if(fast!=NULL)
        fast=fast->next;
        slow=slow->next;
        if(slow==fast)
        {
            // We always get slow and fast at same node after rotating in a cycle because fast is moving
            // two step while slow is moving one step;
        intersection= slow;
        break;
        }
    }
    if(slow==NULL || fast==NULL)
    return head;
    Node *slow1=head;
    while(slow1!=intersection)
    {
        // In this we are moving fast and slow1 pointer one by one after making slow1 to head node because we already find it at same location in a cycle
        // and they will come to begin node from which loop starts. This logic comes from A+B= k*C, where A is the distance
        // of slow to begin node and B is the distance from begin node to fast pointer and when we move fast pointer by A distance then slow
        // and fast will meet at begin node.
        slow1=slow1->next;
        intersection=intersection->next;
    }
    Node *temp=intersection;
    while(temp->next!=intersection)
    {
        // This is for just removing Loop.
        temp=temp->next;
    }
    temp->next=NULL;
    return head;
}
