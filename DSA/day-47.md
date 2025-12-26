Node *mergeLL(Node *&first, Node *&second)
{
       if(first==NULL)
	   return second;
	   if(second==NULL)
	   return first;
	   Node *newe=new Node(-1);
	   Node *ans=newe;
     while(first!=NULL && second!=NULL)
	   {
		   if(first->data<second->data)
		   {
                ans->child=first;
				ans=first;
				first=first->child;
		   }
		   else
		   {
			   ans->child=second;
			   ans=second;
			   second=second->child;
		   }
	   }
	   while(first!=NULL)
	   {
		   ans->child=first;
				ans=first;
				first=first->child;
	   }
	   while(second!=NULL)
	   {
		    ans->child=second;
			   ans=second;
			   second=second->child;
	   }
return newe->child;
}
Node* flattenLinkedList(Node* head) 
{
	if(head==NULL || head->next==NULL)
	{
		return head;
	}
	Node *left=head;
	Node *right=flattenLinkedList(head->next);
	left->next=NULL;
	return mergeLL(left,right);
	

}
