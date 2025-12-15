#include <bits/stdc++.h> 
Node<int>* reverse(Node<int>* head){
     Node<int>* curr=head;
     Node<int>* prev=NULL;
     Node<int>* currnext=head;
     while(curr!=NULL){
      currnext=curr->next;
        curr->next=prev;
        prev=curr;
         curr=currnext;
         } 
         return prev;  

}

void insertAtTail(Node<int>* &head, Node<int>* &tail,int digit){
Node<int>* res=new Node<int>(digit);
if(head == NULL){
head=res;
tail=res;
        return;
        }
else{
tail->next=res;
tail=res;
    }

}

Node<int>* add(Node<int>* first, Node<int>* second){
int carry=0;
    Node<int>* head=NULL;
    Node<int>* tail=NULL;
    while(first !=NULL ||second!=NULL || carry!=0){
        int a=0,b=0;
        if(first!=NULL){
            a=first->data;
            first=first->next;
        }
        if(second!=NULL){
            b=second->data;
            second=second->next;
        }
      int sum=a+b+carry;
           int digit=sum%10;
           insertAtTail(head,tail,digit);
           carry=sum/10;
           }
return head;

}

Node<int>* addTwoLists(Node<int>* first, Node<int>* second) {
first=reverse(first);
second=reverse(second);
    Node<int>* res=add(first,second);
    res=reverse(res);
    return res;

}
