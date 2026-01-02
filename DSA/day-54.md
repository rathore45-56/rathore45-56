vector<int> rotateArray(vector<int> arr, int k) {
    int n = arr.size();
    int c=0;
    vector<int> temp(n);
    for (int i = k; i < n; i++) {
          temp[c++]=arr[i];
    }
    for(int i=0;i<k;i++)
    { 
        temp[c++]=arr[i];
    }
    arr = temp;
    return arr;

}
