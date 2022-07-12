# Bubble Sort
The Bubble Sort, though inefficient, is very simple. The bubble sort works by iterating through the list of numbers and swapping any two adjacent numbers when the one on the right is smaller than the one on the left. For example, with the list below, 39 and 12 get swapped as 12 is smaller. Then, with 39 in the second position, 39 and 18 get swapped as 18 is smaller. Then, if nothing is swapped during an entire run through, the sort is complete. At least, that's how it is implemented below. The complexity of this function is $O(n^2)$.


```python
def bubblesort(numbers):
    swapped = False
    for n in range(len(numbers)-1, 0, -1):
        for i in range(n):
            if numbers[i] > numbers[i + 1]:
                swapped = True
                numbers[i], numbers[i + 1] = numbers[i + 1], numbers[i]       
        if not swapped:
            return
numbers = [39, 12, 18, 85, 72, 10, 2, 18]
print("Unsorted list is,")
print(numbers)
bubblesort(numbers)
print("Sorted Array is, ")
print(numbers)
```