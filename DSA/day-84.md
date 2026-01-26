class Solution {
    public:
    int solve(Node* root)
    {
        int count=0;
        queue<Node *>q;
        q.push(root);
        q.push(NULL);
        while(!q.empty())
        {
            Node *temp=q.front();
            q.pop();
            if(temp==NULL)
            {  
                if(!q.empty())
                {
                    q.push(NULL);
                    count++; 
                }
            }
            else
            {
                if(temp->left)
                q.push(temp->left);
                if(temp->right)
                q.push(temp->right);
            }
        }
        return count;
        
    }
  public:
    int height(Node* root) {
        // code here
       int count= solve(root);
       return count;
    }
};
