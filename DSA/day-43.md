class Solution {
  public:
    bool isPalindrome(Node *head) {
        Node *tail=head;
        Node *prev=head;
        while(tail->next!=NULL)
        {
            prev=tail;
            tail=tail->next;
        }
        Node *temp=head;
        while(temp!=tail)
        {
            if(temp->data!=tail->data)
            return false;
           temp=temp->next;
            prev->next=NULL;
            prev=temp;
            tail=temp;
            while(tail->next!=NULL)
            {
            prev=tail;
            tail=tail->next;
            }
        }
        return true;
    }
};
