#include <bits/stdc++.h> 
int frogJump(int n, vector<int> &heights)
{
   n--;

int prev = 0;

int curr = abs(heights[1] - heights[0]);

 

for(int i=2; i<=n; i++)

{

int ans = min((prev + abs(heights[i-2] - heights[i])), (curr + abs(heights[i-1]-heights[i])));

prev = curr;

curr = ans;

}

 

return curr;
}
