# Time-Complexities
Explain the time complexity of codes - depicting their Run Time Analysis


Try to guess the time complexity of some curated expamples having functions..!!!!

```cpp
int Example1(int n) {
   int count = 0;                         //O(1)  n=10
   for (int i = n; i > 0; i /= 2) {      // n,n/2,n/4,.....1 = O(log n) 10,5,2,1,0
       for (int j = 0; j < i; j++) {      //O(k)=O(n) 
           count += 1;                    O(1)
       }
   }
   return count;
}
```

Answer: O(1)+O(n*log n)*O(1)= O(n*logn)

```cpp
void Example2(int a = 0, int n) {
   int i = n;                               O(1)
   while (i > 0) {                          O(logn)
       a += i;                              O(1)
       i /= 2;                              O(1)
   }
}
```

Answer: O(1)+O(logn)(O(1)+O(1))=O(logn)

```cpp
void Example3(int n) {
   int count = 0;                                     O(1)
   for (int i=n/2; i<=n; i++) {                       O(n/2)= O(n) 
       for (int j=1; j<=n; j = 2 * j) {               O(logn) 
           for (int k=1; k<=n; k = k * 2) {           O(logn)
               count++;                               O(1)
           }
       }
   }
}
```

Answer:O(1)+O(n/2)*O(2^n)*O(2^n)=O(n*(logn)^2)

```cpp
void Example4(int n) {
   int count = 0;                            O(1) n=10
   for (int i=0; i<n; i++)                   O(n) 0-9
       for (int j=i; j< i*i; j++)            O(n^2) 0,1, (2)2,3/ (3),3,4,5,6,7,8/ (4),4,5,6,7,8,9,10,11,12,13
           if (j%i == 0)                     
           {
               for (int k=0; k<j; k++)       O(n^2) 0,1,2,3
                   cout<<"*";                O(1)
           }
}
```

Answer: O(n*n^2*n/2)=n^5

## FUN FACT

What is your observation?
What does it mean when we say that the Merge Sort (MS) algorithm is asymptotically more efficient than the Bubble Sort (BS) algorithm? Support your choice with an explanation.

1. MS will always be a better choice for small inputs
2. MS will always be a better choice for large inputs
3. BS will always be a better choice for small inputs
4. MS will always be a better choice for all inputs

My explaination : 2. Asymptotically Merge Sort ranks better than Bubble Sort when large data sets are compared, because for merge sort, worst case and average case has same complexities O(n log n) whereas calculating the worst case of bubble sort O(n2). So it will always be advisable to neglect O(n2) and choose O(logn)/Harmonic progressions. Bubble sort works better for small set of datas, whereas Merge sort has consistent seed on any data set.                                                                                  I would have chosen Answer 4 as my final answer, but                                                                                                                           
The Big O notation of the best case scenario of Bubble sort is O(n), so there are some cases in which Bubbe sort will out perform Merge sort, hence I go with the most obvious answer that is option 2. Merge Sort will always be a better choice for large inputs.
