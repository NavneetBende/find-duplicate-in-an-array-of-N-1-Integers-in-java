Duplicate in an array of N+1 integers in Java
Here, in this page we will discuss the program to find the duplicate in an array of N+1 integers in Java programming . We are Given an array of integers Arr containing N+1 integers where each integer is in the range [1, N] inclusive.

Given an array of n elements containing elements ranging from 0 to n-1, any of these numbers can appear any number of times. Find these repeating numbers in O(n) while only using constant memory space.

Duplicate in an array of N+1 integers
Algorithm :
We’ll start with two variables, I and j, and work our way up.
We will loop until I reach the last element or find a repeated element.
We will pre-increment the j value in order to compare elem to the next elem.
If we don’t find elem, we’ll raise I because j will be pointing to the last elem, and then reposition j with i.
Code in Java
Run

import java.io.*;
import java.util.*;
public
class Main {
    static int findduplicate(int[] arr, int n) {

        // return -1 because in these cases
        // there can not be any repeated element

        if (n <= 1) return -1;
        // initialize fast and slow
        int slow = arr[0];
        int fast = arr[arr[0]];

        // loop to enter in the cycle
        while (fast != slow) {
            // move one step for slow
            slow = arr[slow];
            // move two step for fast
            fast = arr[arr[fast]];
        }
        // loop to find entry point of the cycle
        fast = 0;
        while (slow != fast) {
            slow = arr[slow];
            fast = arr[fast];
        }
        return slow;
    }
    // Driver Code

    public
    static void main(String args[]) {
        int[] arr = {1, 2, 3, 4, 5, 6, 3};
        int n = arr.length;
        System.out.print(findduplicate(arr, n));
    }
}
Output
3
 
Note
Time Complexity : O(n) Auxiliary Space : O(1)
Related Pages
Given an array which consists of only 0, 1 and 2

Move all the negative elements to one side of the array

Find the Union and Intersection of the two sorted arrays

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 2
Run
import java.util.*;
public
class Main {
    public static void main(String args[])
    {
        int numRay[] = { 0, 4, 3, 2, 7, 8, 2, 3, 1 };
 
        for (int i = 0; i < numRay.length; i++) {
            numRay[numRay[i] % numRay.length]
                = numRay[numRay[i] % numRay.length]
                  + numRay.length;
        }
        System.out.println("The repeating elements are : ");
        for (int i = 0; i < numRay.length; i++) { if (numRay[i] >= numRay.length * 2) {
                System.out.println(i + " ");
            }
        }
    }
}
Output
The repeating elements are : 
2 
3 
