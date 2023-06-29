QUESTION 1:-
BINARY SERACH:-
Method 1:-
Binary Search

# Iterative Binary Search Function method Python Implementation  
# It returns index of n in given list1 if present,   
# else returns -1   
def binary_search(list1, n):  
    low = 0  
    high = len(list1) - 1  
    mid = 0  
  
    while low <= high:  
        # for get integer result   
        mid = (high + low) // 2  
  
        # Check if n is present at mid   
        if list1[mid] < n:  
            low = mid + 1  
  
        # If n is greater, compare to the right of mid   
        elif list1[mid] > n:  
            high = mid - 1  
  
        # If n is smaller, compared to the left of mid  
        else:  
            return mid  
  
            # element was not present in the list, return -1  
    return -1  
  
  
# Initial list1  
list1 = [12, 24, 32, 39, 45, 50, 54]  
n = 45  
  
# Function call   
result = binary_search(list1, n)  
  
if result != -1:  
    print("Element is present at index", str(result))  
else:  
    print("Element is not present in list1")  

    
METHOD 2:-
# Iterative Binary Search Function method Python Implementation  
# It returns index of n in given list1 if present,   
# else returns -1   
def binary_search(list1, n):  
    low = 0  
    high = len(list1) - 1  
    mid = 0  
  
    while low <= high:  
        # for get integer result   
        mid = (high + low) // 2  
  
        # Check if n is present at mid   
        if list1[mid] < n:  
            low = mid + 1  
  
        # If n is greater, compare to the right of mid   
        elif list1[mid] > n:  
            high = mid - 1  
  
        # If n is smaller, compared to the left of mid  
        else:  
            return mid  
  
            # element was not present in the list, return -1  
    return -1  
  
  
# Initial list1  
list1 = [12, 24, 32, 39, 45, 50, 54]  
n = 45  
  
# Function call   
result = binary_search(list1, n)  

QUESTION 2:-

# MergeSort in Python


def mergeSort(array):
    if len(array) > 1:

        #  r is the point where the array is divided into two subarrays
        r = len(array)//2
        L = array[:r]
        M = array[r:]

        # Sort the two halves
        mergeSort(L)
        mergeSort(M)

        i = j = k = 0

        # Until we reach either end of either L or M, pick larger among
        # elements L and M and place them in the correct position at A[p..r]
        while i < len(L) and j < len(M):
            if L[i] < M[j]:
                array[k] = L[i]
                i += 1
            else:
                array[k] = M[j]
                j += 1
            k += 1

        # When we run out of elements in either L or M,
        # pick up the remaining elements and put in A[p..r]
        while i < len(L):
            array[k] = L[i]
            i += 1
            k += 1

        while j < len(M):
            array[k] = M[j]
            j += 1
            k += 1


# Print the array
def printList(array):
    for i in range(len(array)):
        print(array[i], end=" ")
    print()


# Driver program
if __name__ == '__main__':
    array = [6, 5, 12, 10, 9, 1]

    mergeSort(array)

    print("Sorted array is: ")
    printList(array)

METHOD 2:-

def merge_sort(list1, left_index, right_index):  
    if left_index >= right_index:  
        return  
  
    middle = (left_index + right_index)//2  
    merge_sort(list1, left_index, middle)  
    merge_sort(list1, middle + 1, right_index)  
    merge(list1, left_index, right_index, middle)  
  
  
    # Defining a function for merge the list  
def merge(list1, left_index, right_index, middle):  
  
  
   # Creating subparts of a lists  
    left_sublist = list1[left_index:middle + 1]  
    right_sublist = list1[middle+1:right_index+1]  
  
    # Initial values for variables that we use to keep  
    # track of where we are in each list1  
    left_sublist_index = 0  
    right_sublist_index = 0  
    sorted_index = left_index  
  
    # traverse both copies until we get run out one element  
    while left_sublist_index < len(left_sublist) and right_sublist_index < len(right_sublist):  
  
        # If our left_sublist has the smaller element, put it in the sorted  
        # part and then move forward in left_sublist (by increasing the pointer)  
        if left_sublist[left_sublist_index] <= right_sublist[right_sublist_index]:  
            list1[sorted_index] = left_sublist[left_sublist_index]  
            left_sublist_index = left_sublist_index + 1  
        # Otherwise add it into the right sublist  
        else:  
            list1[sorted_index] = right_sublist[right_sublist_index]  
            right_sublist_index = right_sublist_index + 1  
  
  
        # move forward in the sorted part  
        sorted_index = sorted_index + 1  
  
       
    # we will go through the remaining elements and add them  
    while left_sublist_index < len(left_sublist):  
        list1[sorted_index] = left_sublist[left_sublist_index]  
        left_sublist_index = left_sublist_index + 1  
        sorted_index = sorted_index + 1  
  
    while right_sublist_index < len(right_sublist):  
        list1[sorted_index] = right_sublist[right_sublist_index]  
        right_sublist_index = right_sublist_index + 1  
        sorted_index = sorted_index + 1  
  
list1 = [44, 65, 2, 3, 58, 14, 57, 23, 10, 1, 7, 74, 48]  
merge_sort(list1, 0, len(list1) -1)  
print(list1)  

QUESTION 3:-
QUICK SORT:-
Quick sort in Python

# function to find the partition position
def partition(array, low, high):

  # choose the rightmost element as pivot
  pivot = array[high]

  # pointer for greater element
  i = low - 1

  # traverse through all elements
  # compare each element with pivot
  for j in range(low, high):
    if array[j] <= pivot:
      # if element smaller than pivot is found
      # swap it with the greater element pointed by i
      i = i + 1

      # swapping element at i with element at j
      (array[i], array[j]) = (array[j], array[i])

  # swap the pivot element with the greater element specified by i
  (array[i + 1], array[high]) = (array[high], array[i + 1])

  # return the position from where partition is done
  return i + 1

# function to perform quicksort
def quickSort(array, low, high):
  if low < high:

    # find pivot element such that
    # element smaller than pivot are on the left
    # element greater than pivot are on the right
    pi = partition(array, low, high)

    # recursive call on the left of pivot
    quickSort(array, low, pi - 1)

    # recursive call on the right of pivot
    quickSort(array, pi + 1, high)


data = [8, 7, 2, 1, 0, 9, 6]
print("Unsorted Array")
print(data)

size = len(data)

quickSort(data, 0, size - 1)

print('Sorted Array in Ascending Order:')
print(data)
if result != -1:  
    print("Element is present at index", str(result))  
else:  
    print("Element is not present in list1")  
METHOD 2:-


def quicksort(alist, start, end):
    '''Sorts the list from indexes start to end - 1 inclusive.'''
    if end - start > 1:
        p = partition(alist, start, end)
        quicksort(alist, start, p)
        quicksort(alist, p + 1, end)
 
 
def partition(alist, start, end):
    pivot = alist[start]
    i = start + 1
    j = end - 1
 
    while True:
        while (i <= j and alist[i] <= pivot):
            i = i + 1
        while (i <= j and alist[j] >= pivot):
            j = j - 1
 
        if i <= j:
            alist[i], alist[j] = alist[j], alist[i]
        else:
            alist[start], alist[j] = alist[j], alist[start]
            return j
 
 
alist = input('Enter the list of numbers: ').split()
alist = [int(x) for x in alist]
quicksort(alist, 0, len(alist))
print('Sorted list: ', end='')
print(alist)
def partition (a, start, end):  
    i = (start - 1)  
    pivot = a[end] # pivot element  
      
    for j in range(start, end):  
        # If current element is smaller than or equal to the pivot  
        if (a[j] <= pivot):  
            i = i + 1  
            a[i], a[j] = a[j], a[i]  
      
    a[i+1], a[end] = a[end], a[i+1]  
  
    return (i + 1)  
      
# function to implement quick sort   
def quick(a, start, end): # a[] = array to be sorted, start = Starting index, end = Ending index      
    if (start < end):  
        p = partition(a, start, end) # p is partitioning index  
        quick(a, start, p - 1)  
        quick(a, p + 1, end)  
  
          
def printArr(a): # function to print the array  
    for i in range(len(a)):  
        print (a[i], end = " ")  
  
      
a = [68, 13, 1, 49, 58]  
print("Before sorting array elements are - ")  
printArr(a)  
quick(a, 0, len(a)-1)  
print("\nAfter sorting array elements are - ")  
printArr(a)  


