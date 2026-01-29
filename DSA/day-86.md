<code/>
class Solution {
// This takes O(n*2) Time complexity and O(height of binary tree) Space Complexity.//
    private:
    int height(struct Node *node)
    {
        if(node==NULL)
        return 0;
        int left1=height(node->left);
        int right1=height(node->right);
        int ans=max(left1,right1)+1;
        return ans;
    }
  public:
    int diameter(Node* root) {
      if(root==NULL)
      {
          return 0;
      }
      int left1=diameter(root->left);
      int right1=diameter(root->right);
      int whole= height(root->left)+height(root->right);
      int ans=max(left1,max(right1,whole));
      return ans;
    }
};


# Optimised Solution #
->
<code/>
class Solution {
// This takes O(n) Time Complexity and O(height of binary tree) Space Complexity.//
    private:
    pair<int,int>Solve(struct Node *node)
    {
        if(node==NULL)
        {
            pair<int,int>p=make_pair(0,0);
            return p;
        }
        pair<int,int>left=Solve(node->left);
        pair<int,int>right=Solve(node->right);
        int a=left.first;
        int b=right.first;
        int c= left.second+right.second;
        pair<int,int>ans;
        ans.first= max(a,max(b,c));
        ans.second=max(left.second,right.second)+1;
        return ans;
    }
  public:
    int diameter(Node* root) {
      return Solve(root).first;    
    }
};
