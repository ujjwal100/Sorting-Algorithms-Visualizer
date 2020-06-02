# Sorting Algorithms Visualizer
## Overview
This project is a graphical simulation of the commonly used Sorting Algorithms like **Merge Sort**, **Quick Sort** and
also **Bubble Sort**. Designed using the _Tkinter_ GUI Library of Python, this project serves to visualize the working of each
of these algorithms in practice, using randomly generated arrays of numeric data.
## Conceptual Background

Sorting refers to arranging data in a particular format. Sorting algorithm specifies the way to arrange data in a 
particular order. Most common orders are in numerical or lexicographical order.
The importance of sorting lies in the fact that data searching can be optimized to a very high level, if data is stored in 
a sorted manner. Sorting is also used to represent data in more readable formats.<br> 
Let's take a deep dive into each of the three sorting
algorithms and explore the difference between these algorithmic paradigms. 
## Bubble Sort
Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.
Below is the pseudocode for Bubble Sort followed by its asymptotic analysis. 

### _Pseudocode_
```py
begin BubbleSort(list)

   for all elements of list
      if list[i] > list[i+1]
         swap(list[i], list[i+1])
      end if
   end for
   
   return list
   
end BubbleSort
```
### _Asymptotic Analysis_
- Worst and Average Case Time Complexity: O(n*n)
- Best Case Time Complexity: O(n)
- Auxiliary Space: O(1)

## Merge Sort
Merge Sort is a **Divide and Conquer** algorithm. It divides input array in two halves, calls itself 
for the two halves and then merges the two sorted halves. The merge() function is used for 
merging two halves. The **merge()** function is the key process that assumes that the two halves
are sorted and merges the two sorted sub-arrays into one. Let's take a look at the pseudocode and asymptotic analysis.

### _Pseudocode_
```python
procedure mergesort( var a as array )
   if ( n == 1 ) return a

   var l1 as array = a[0] ... a[n/2]
   var l2 as array = a[n/2+1] ... a[n]

   l1 = mergesort( l1 )
   l2 = mergesort( l2 )

   return merge( l1, l2 )
end procedure

procedure merge( var a as array, var b as array )

   var c as array
   while ( a and b have elements )
      if ( a[0] > b[0] )
         add b[0] to the end of c
         remove b[0] from b
      else
         add a[0] to the end of c
         remove a[0] from a
      end if
   end while
   
   while ( a has elements )
      add a[0] to the end of c
      remove a[0] from a
   end while
   
   while ( b has elements )
      add b[0] to the end of c
      remove b[0] from b
   end while
   
   return c
	
end procedure
```

### _Asymptotic Analysis_
- Best, Worst and Average Case Time Complexity : O(n*log(n))
- Auxiliary Space: O(n)

## Quick Sort
Like Merge Sort, QuickSort is a **Divide and Conquer** algorithm. It uses the **Partition()** function to pick an element as pivot 
and partitions the given array around the picked pivot. Quicksort then partitions the given array and calls itself recursively twice 
to sort the two resulting subarrays.

### _Pseudocode_
```python
function Partition(left, right, pivot)
   leftPointer = left
   rightPointer = right - 1

   while True do
      while A[++leftPointer] < pivot do
         //do-nothing            
      end while
		
      while rightPointer > 0 && A[--rightPointer] > pivot do
         //do-nothing         
      end while
		
      if leftPointer >= rightPointer
         break
      else                
         swap leftPointer,rightPointer
      end if
		
   end while 
	
   swap leftPointer,right
   return leftPointer
	
end function

procedure quickSort(left, right)

   if right-left <= 0
      return
   else     
      pivot = A[right]
      partition = Partition(left, right, pivot)
      quickSort(left,partition-1)
      quickSort(partition+1,right)    
   end if		
   
end procedure
```
### _Asymptotic Analysis_
- Worst Case Time Complexity: O(n*n)
- Best and Average Case Time Complexity: O(n*log(n))
- Auxiliary Space: O(1)
## Conclusion
This Sorting Algorithms Visualizer Project can be of great use to learners getting introduced to Sorting. This visual aid shall help 
them grasp the underlying algorithms easily and enable them to implement these better, in future.
