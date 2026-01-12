class kQueues {
    int *arr;
    int *front;
    int *rear;
    int *next;
    int freespot;
  public:
    kQueues(int n, int k) {
    // In this i am initialising front and rear array with -1 of size k(Number of queues) and next array with index+1 to particular index //.
        arr=new int[n];
        front=new int[k];
        rear=new int[k];
        for(int i=0;i<k;i++)
        {
            front[i]=-1;
            rear[i]=-1;
        }
        next=new int[n];
        for(int i=0;i<n;i++)
        {
            next[i]=i+1;
        }
        next[n-1]=-1;
        freespot=0;
    }
    void enqueue(int x, int i) {
    // In this first i am checking for first element push then i am intitalising front with the particular index and for rest first i am initialising next array value 
    //  of rear value of that particular index(function index) to index(freespot) //.
        if(freespot==-1)
        return;
        int index=freespot;
        freespot=next[index];
        if(front[i]==-1)
        {
            front[i]=index;
        }
        else
        {
            next[rear[i]]=index;
        } 
        // After above condition i am initialising next array of that particular index to -1 as there is no slot for other values on that index
        // then i am initialising rear array of a particular index to the previous freespot.
        next[index]=-1;
        rear[i]=index;
        arr[index]=x;
      } 
        int dequeue(int i) { 
        // In this i am taking first front value of a particular index then updating front value to next value after checking next array value of the index(nextarray index)//.
        // then i am initialising next array of particular index to available freespot so that i can initialise freespot to that index and make that index to 
        // to be useful for next push operations.
        if(front[i]==-1)
        return -1;
        int index=front[i];
        front[i]=next[index];
        next[index]=freespot;
        freespot=index;
        return arr[index];
    }
    bool isEmpty(int i) {
        if(front[i]==-1)
        return 1;  
        return 0;
    }
    bool isFull() {
        if(freespot==-1)
        return 1; 
        return 0;
    }
};
