Removing duplicate elements in a sorted array
Here in this page we will discuss the program for removing duplicate elements in a sorted array in C++ programming language. We will discuss different approaches to solve the given problem. We are given with an array and need to print the array after removing the duplicates.

removing-duplicate-element-in-an-array-cpp
While loop in C
Example :
Input : arr[8]= [10, 10, 20, 30, 30, 40, 40, 40]
Output : 10 20 30 40
Method Discussed :
Method 1 : Using Set Data Structure
Method 2 : Without Using Extra Space.
Let’s discuss both methods one by one in brief.

Method 1 :
Declare a set data structure.
Insert the elements of array in set.
Start iterating in set and print the set elements.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Related Pages
Finding the Longest Palindrome in an Array

Counting Distinct Elements in an Array

Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Finding Minimum scalar product of two vectors

Removing dupliacte elements
Set in C++ STL
Sets are a type of associative containers in which each element has to be unique because the value of the element identifies it. The values are stored in a specific order.
Method 1 : Code in C++
Run
#include<bits/stdc++.h>

using namespace std;
int main(){
set<int>s;
int arr[] = {10, 10, 20, 30, 30, 30, 40};
int n = sizeof(arr)/sizeof(arr[0]);
for(int i=0; i<n; i++)
s.insert(arr[i]);
for(auto it = s.begin(); it != s.end(); it++)
cout<<*it<<" ";
}
Output :
10 20 30 40
Method 2 :
In this method we will not use extra space.

Create a function say duplicate that will return the index value.
if(n==0) or (n==1) then return n.
Otherwise take a variable say j set j =0;
Run a loop from index 0 to n-1
If(arr[i]!=arr[i+1]), Then set arr[j++] = arr[i]
Finally, return the value of j
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 2 : Code in C++
Run
#include<bits/stdc++.h>

using namespace std;

int duplicates(int arr[], int n)
{
    if (n==0 || n==1)
      return n;

    int j = 0;

    for (int i=0; i < n-1; i++)
        if (arr[i] != arr[i+1])
           arr[j++] = arr[i];

    arr[j++] = arr[n-1];

    return j;
}

// Driver code
int main()
{
   int arr[] = {10, 20, 20, 30, 40, 40, 40, 50, 50};
   int n = sizeof(arr) / sizeof(arr[0]);

   n = duplicates(arr, n);

   for (int i=0; i<n; i++)
    cout << arr[i] << " ";

   return 0;
}
Output :
10 20 30 40 50
