#include <bits/stdc++.h> 
string specificOrder(string & x, string & y) {
    string op="";
    int count[26]={0};
    for(int i=0;i<x.length();i++) {
        char temp=x[i];
        int number= temp-'a';
        count[number]++;
    }
    for(int i=0;i<y.length();i++) {
        char temp=y[i];
        int number= temp-'a';
        while(count[number]) {
            op.push_back(y[i]);
            count[number]--;
        }
    }
    for(int i=0;i<26;i++) {
        while(count[i]) {
            char c=i+'a';
            op.push_back(c);
            count[i]--;
        }
    }
    return op;
}
