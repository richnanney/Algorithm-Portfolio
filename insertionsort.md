# Insertion Sort
Insertion Sort works similarly to how we may organize a deck of cards. Going through the list of numbers and, upon finding a number that is out of position, simply moving it to its correct positoin. For example, with the list below, we would see 12 and 11 and move 11 to the front. Then, seeing 5, would bring 5 to the front. Then, upon seeing 6, would move it into position between 5 and 11. The complexity of this algorithm is $O(n^2)$.



```python
def insertionSort(numbers):
    for i in range(1, len(numbers)):
        key = numbers[i]
        j = i-1
        while j >=0 and key < numbers[j] :
                numbers[j+1] = numbers[j]
                j -= 1
        numbers[j+1] = key
 
numbers = [12, 11, 13, 5, 6]
insertionSort(numbers)
print ("Sorted array is:")
for i in range(len(numbers)):
    print (numbers[i])
```