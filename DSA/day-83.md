void countleaf(BinaryTreeNode<int> *root, int &count)
{
  if(root==NULL)
  return;

  countleaf(root->left,count);
  if(root->left==NULL && root->right==NULL)
  count++;

  countleaf(root->right,count);
}
int noOfLeafNodes(BinaryTreeNode<int> *root){
 int count=0;
 countleaf(root,count);
 return count;
}
