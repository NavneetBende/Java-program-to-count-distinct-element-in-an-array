Count distinct element in an array in Java
In this section, we will learn, how to Count distinct element in an array in java language.

Given an integer array, we have to print all the distinct element of the input array. input array may contain duplicate elements, we have to print the count of distinct elements.

java Program to Counting distinct elements
Methods Discussed are :
Method 1 : Using Two loops
Method 2 : Using hash Map
Let’s discuss each method one by one,

Method 1 :
In this method we will count the frequency of each elements using two for loops.

To check the status of visited elements create a array of size n and a variable say count_dis=0 to count the distinct element.
Run a loop from index 0 to n and check if (visited[i]==1) then skip that element.
Run a loop from index i+1 to n
Check if(arr[i]==arr[j]), then set visited[j]=1.
After complete iteration of inner for loop and increment the value of count_dis
At last print the value count_dis
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(n)
Method 1 : Code in Java
Run
import java.util.Arrays;

class Main
{
   public static void countFreq(int arr[], int n)
   {
         boolean visited[] = new boolean[n];
         Arrays.fill(visited, false);
         int count_dis=0;
         // Traverse through array elements and
         // count frequencies
         for (int i = 0; i < n; i++) {

            // Skip this element if already processed
            if (visited[i] == true)
             continue;

           
            for (int j = i + 1; j < n; j++) {
                if (arr[i] == arr[j]) {
                   visited[j] = true;
                   
                }
            }
            count_dis = count_dis+1;
   }
   System.out.println(count_dis);
  }

   // Driver code
   public static void main(String []args)
   {
      int arr[] = new int[]{10, 30, 40, 20, 10, 20, 50, 10};
      int n = arr.length;
      countFreq(arr, n);
   }
}
Output
5
Related Pages
Sorting elements of an array by frequency

Finding the Longest Palindrome in an Array

Finding  Repeating elements in an Array

Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Method 2 :
In this method we will count use hash-map to count the frequency of each elements.

Declare a hash map and a variable count_dis=0.
Start iterating over the entire array
If element is present in map, then increase the value of frequency by 1.
Otherwise, insert that element in map.
After complete iteration over array, print the size of map.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Method 2 : Code in Java
Run
import java.util.*;
import java.util.Arrays;

class Main
{
   static void countFreq(int arr[], int n)
   {
      Map<Integer, Integer> mp = new HashMap<>();
      int count_dis=0;
      // Traverse through array elements and
      // count frequencies
      for (int i = 0; i < n; i++)
      {
         if (mp.containsKey(arr[i]))
         {
           mp.put(arr[i], mp.get(arr[i]) + 1);
         }
         else
         {
           mp.put(arr[i], 1);
         }
     }
     
     System.out.println(mp.size());
  }
  // Driver code
  public static void main(String []args)
  {
       int arr[] = new int[]{10, 40, 50, 20, 10, 20, 30, 10};
       int n = arr.length;
       countFreq(arr, n);
  }
}
Output
5
