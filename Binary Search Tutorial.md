# Binary Search

## How Binary Search Works
Binary Search works by reducing Problem size by half
at every step, for example lets say you wanted to open
a particualr page in your book. 

If we follow binary search, you just open the middle page of the book and check if that is the page you are looking for
, if not you just its either lies in first half i.e. page1 to pagemid or second half i.g. pagemid to pageend
based on that you look in one of the half.
Now at the next step as well you can reduce your problem size in half again


 ![binary seach example.png](:storage\a65a5247-59de-43c9-a127-3ce2edc99d42/c04e1327.png)

## Time Complexity
Worst case for binary search occurs when the element is not in array 

Still binary search allow us to locate an element in $O(log2 n)$. Also its important to note that binary search
only works if array is already sorted, otheriwise you also have to add the complexity of sorting the array



## Questions to solve
1. Implement recursive and iterative binary search
2. [Given an array A[] and a number x, check for pair in A[] with sum as x - GeeksforGeeks](https://www.geeksforgeeks.org/given-an-array-a-and-a-number-x-check-for-pair-in-a-with-sum-as-x/)
3. [Pythagorean Triplet in an array - GeeksforGeeks](https://www.geeksforgeeks.org/find-pythagorean-triplet-in-an-unsorted-array/)
4. [Equilibrium index of an array - GeeksforGeeks](https://www.geeksforgeeks.org/equilibrium-index-of-an-array/)

