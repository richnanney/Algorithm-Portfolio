# Selection Sort
The selection sort is terribly inefficient. It scans the entire list of numbers and, upon determining which number is smallest, swaps that number with the number taking up its position. So, with the numbers below, the number 11 gets swapped with 64, putting 11 in the first position. Then 12 and 25 are swapped, putting 12 in the second position, etc. The effeciency of this algorithm is $O(n^2)$.


```python
numbers = [64, 25, 12, 22, 11]
 
for i in range(len(numbers)):
    min_idx = i
    for j in range(i+1, len(numbers)):
        if numbers[min_idx] > numbers[j]:
            min_idx = j
    numbers[i], numbers[min_idx] = numbers[min_idx], numbers[i]
 

print ("Sorted array")
for i in range(len(numbers)):
    print(numbers[i])
 ```