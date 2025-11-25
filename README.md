## Hi there 👋
## 🚀 Data Structures & Algorithms Progress

I am actively enhancing my problem-solving skills by practicing Data Structures & Algorithms with consistent daily learning and coding. I have completed core foundational concepts including:

- Arrays
- Strings
- Recursion
- Sorting & Searching

I have solved multiple problems related to these topics while focusing on optimal solutions and clean code structure.  
Currently, I am working on advanced topics, and my upcoming roadmap includes:

- Object-Oriented Programming (OOP)
- Linked List
- Stack & Queue
- Trees & Binary Search Trees
- Graphs (BFS, DFS, Shortest Path)
- Dynamic Programming (DP)

📍 My goal is to master data structures required for real-world technical interviews and maintain daily GitHub commits by solving topic-wise problems.

### 🧠 DSA Progress & Badges

### 📅 Topic-wise Roadmap
| Topic | Status |
|-------|--------|
| Arrays | ✔ Completed |
| Strings | ✔ Completed |
| Recursion | ✔ Completed |
| Sorting | ✔ Completed |
| Searching | ✔ Completed |
| OOP | 🔄 In Progress |
| Linked List | ⏳ Upcoming |
| Stack & Queue | ⏳ Upcoming |
| Trees & BST | ⏳ Upcoming |
| Graphs | ⏳ Upcoming |
| Dynamic Programming | ⏳ Upcoming |

### 📌 Goal
**Solve 300+ DSA questions in 60 days and maintain daily GitHub activity.**

💡## **About Me**
- 👨‍🎓 B.Tech (CSE), Completed 2024
- 🧠 Strong foundation in Data Structures & Algorithms
- 🏆 College Chess Champion | 4th Prize District Math Competition<!--
**rathore45-56/rathore45-56** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

### 📌 **Current Goals**
- 📚 Complete DSA topic-wise with consistency
- 📝 Push daily commits and maintain progress on GitHub
- 💻 Work on impactful real-world projects

💡## **About Me**
- 👨‍🎓 B.Tech (CSE), Completed 2024
- 🧠 Strong foundation in Data Structures & Algorithms
- 🏆 College Chess Champion | 4th Prize District Math Competition<!--
**rathore45-56/rathore45-56** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.


---
### 📫 **Contact**
- **Email:** thakur8utkarsh@gmail.com
- **LinkedIn:** https://linkedin.com/in/www.linkedin.com/in/utkarsh-rathore-0178a3237

## 🔥 Day-wise Progress

### **Day 1 – 25 Nov 2025**
- Problems Solved:  2
- Topics Covered:  1
- Lecture(s) Watched:  1
- Notes:  Today i have done 2 problems-> 1.Problem statement
Ninja has been given an assignment by his teacher. He has been given three integers ‘a’,’b’, and ‘c’ which represent the coefficients of the equation “ax + by = c”. His task is to find the initial integral solution of the given equation if a finite solution exists.

For example:

If ‘a’, ‘b’, and ‘c’ are 5, 10, and 10 respectively, the initial integral solution will be 2 and 0 for ‘x’ and ‘y’ respectively.

**💡 Approach Used By me**
-> I did the question using recursion because c has given so I used c as GCD(Greatest Common Divisor). I use base condition where I make "a" as 0(zero) and make y as "c/b" if "c%b==0" otherwise make x and y as     "0". 

**<code/>**
#include <bits/stdc++.h> 
void calculate(int a,int b,int c,int &x,int &y)
{
	if(a==0)
	{
		if(c%b==0)
		{
		x=0;
		y=c/b;
		return;
		}
		else
		{
			x=0;
			y=0;
			return;
		}
		
		
	}
	
	int i,j;

	calculate(b%a,a,c,i,j);
	x=j-(b/a)*i;
	y=i;
}
vector<int> linearEquation(int a, int b, int c)
{
	int x,y;
	calculate(a,b,c,x,y);
	if(x==0&&y==0)
	return {-1,-1};
	return {x,y};

}


2.Problem statement
You have been given a number 'N'. Your task is to find the sum of all even numbers from 1 to 'N' (both inclusive).

Example :

Given 'N' : 6
Sum of all even numbers till 'N' will be : 2 + 4 + 6 = 12

**💡 Approach Used By me**

-> I solved the problem using recursion and use base condition as "n==0" then return 0. Otherwise call function for odd and even terms.

**<code/>**
#include <bits/stdc++.h> 
long long sum=0;
long long evenSumTillN(int n) {
    if(n==0)
    return 0;
    if(n&1)
    {
       
        evenSumTillN(n-1);
    }
    else
    { 
      sum=n+ evenSumTillN(n-2);
      return sum;
    }
}



