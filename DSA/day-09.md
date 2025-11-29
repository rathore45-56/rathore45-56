class Solution {
    private:
     bool cango(vector<vector<int>>b,int n,vector<vector<int>>&maze,int newi,int newj)
   {
       if((newi>=0 && newi<n) && (newj>=0 && newj<n )&& b[newi][newj]==0 && maze[newi][newj]==1)
       return true;
       else
       return false;
   }
    void calculate(vector<vector<int>>b,vector<string>&s,string op,vector<vector<int>>&maze,int iu,int ju,int n)
   {
       if(iu==n-1 && ju==n-1)
       {
           s.push_back(op);
           return;
       }
       b[iu][ju]=1;
       // down
        int newiu=iu+1;
        int newju=ju;
       if(cango(b,n,maze,newiu,newju))
       {
         op.push_back('D');
         calculate(b,s,op,maze,newiu,newju,n);
         op.pop_back();
        }
       // Left
       newiu=iu;
            newju=ju-1;
       if(cango(b,n,maze,newiu,newju))
       {
         op.push_back('L');
         calculate(b,s,op,maze,newiu,newju,n);
         op.pop_back();
        }
       // Right
       newiu=iu;
        newju=ju+1;
       if(cango(b,n,maze,newiu,newju))
       {
         op.push_back('R');
         calculate(b,s,op,maze,newiu,newju,n);
         op.pop_back();
        }
       // Upward
        newiu=iu-1;
         newju=ju;
       if(cango(b,n,maze,newiu,newju))
       {
         op.push_back('U');
         calculate(b,s,op,maze,newiu,newju,n);
         op.pop_back();
         }
       b[iu][ju]=0;
   }
  public:
    vector<string> ratInMaze(vector<vector<int>>& maze) {
        string op="";
        vector<string>s;
        if(maze[0][0]==0)
        {
            return s;
        }
        vector<vector<int>>b=maze;
        int n=maze.size();
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                b[i][j]=0;
            }
        }
        int index1=0,index2=0;
        calculate(b,s,op,maze,index1,index2,n);
        sort(s.begin(),s.end());
        return s;
    }
};
