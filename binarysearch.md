# Binary Search and Linear Search

Originally when making these algorithms, they were done to be juxtaposed, so they were made in parallel. I have preserved the code of each below but elect to keep them together. Mostly because I'm lazy, if I'm being honest with you.

Linear search will simply guess every number in order. 1, then 2, then 3, etc.

The efficiency of the linear search is, at worst, $O(n)$.

Binary search will split the list of numbers in half, then if the number is lower or higher, splits the remaining possible values in half and guesses the middle again. For guessing a number between 1 and 10, that means guessing 5, then if higher guesses 8, etc. You can see what numbers the algorithm will guess in each scenario as a comment in the python code below.

The efficiency of the binary search is, at worst, $O(log(n))$.



```python
import random
def linearSearch(array, answer, low, high):
    for i in range(low, high+1):
        if(array[i] == int(answer)):
            print(f"It took the linear search", i + 1, "tries to get it right!")
            return
    return -1

def binarySearch(array, answer, low, high):
    tries = 0
    while low <= high:
        tries +=1
        mid = (high + low)//2    #guesses 5, 8, 6, 7 // 5, 8, 9, 10 // 5, 2, 1 // 5, 2, 3, 4 
        if array[mid] == answer:
            print(f"It took the binary search", tries, "tries to get it right!")
            return
        elif array[mid] < answer:
            low = mid + 1
        else:
            high = mid - 1
    return -1

array = [1,2,3,4,5,6,7,8,9,10]
answer = random.randint(1,10)
attempt = -1
tries = 0
low = 0
high = 9

while attempt != answer:
    tries += 1
    attempt = int(input("What is your guess? "))
    if attempt > answer:
        print("Nope! Too high.")
    elif attempt < answer:
        print("Nope! Too low")
    else:
        print(f"Nice! You got it. It took you", tries, "attempts!")

linearSearch(array, answer, low, high)
binarySearch(array, answer, low, high)
```