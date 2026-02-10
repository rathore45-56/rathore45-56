<code/>
void deleteNode(LinkedListNode<int> * node) {
    node->data=node->next->data;
    LinkedListNode<int> *node1=node->next;
    node->next=node->next->next;
    delete(node1);

}
