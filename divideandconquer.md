# Quicksort

Quicksrot, like the merge sort, is a divide and conquer algorithm. It picks a number as a pivot and splits up the list of numbers around that pivot. Different versions of the quicksort pick different numbers as their pivot. Mine picks the median number.

I originally wrote this as two seperate functions and have preserved it below. It's decent code, but probably a little ineffecient.

In the worst case scenario, the quick sort is $O(n^2)$. However, it's worth noting that quick sort trends toward a complexity of $O(nlog(n))$ on average.

```python
def divide(numbers):
    if len(numbers) == 0 or len(numbers) == 1:
        return numbers
    else:
        middle = (len(numbers))//2
        left = divide(numbers[:middle])
        right = divide(numbers[middle:])
        combine = conquer(left,right)
        return combine

def conquer(left, right):
    numbers = []
    i = 0
    j = 0
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            numbers.append(left[i])
            i+=1
        else:
            numbers.append(right[j])
            j+=1
    numbers += right[j:]
    numbers += left[i:]
    return numbers

numbers = [5,8,1,6,7,9,10,15,20,25,100,99,188,88,266,200,5,5,5]
answer = divide(numbers)
print(answer)
```