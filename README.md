# Quick_Sort_Algorithm

Next up is Quick sort. Since it uses pivot points, it is slightly more difficult but also much more efficient. 

![image](https://user-images.githubusercontent.com/66803124/118491714-1cf3e500-b6d4-11eb-81b8-9cad1180cb86.png)

As shown above, there is a list of numbers that we want to have sorted in asecending order. 

The Quick sort grabs a number, in this case it uses the last number in the list, and iterates through the entire list with the pivot point number as its comparison. 

This creates two lists on either side of the initial comparison number. The first left to the left is less than pivot and the list to the right is more than pivot.  

Next, we grab the last number that the end of these newly created lists and perform the same function, comparing each number in that list to the comparison. 

We will continue in this manner until everything is properly sorted. 


```
def quick_sort(sequence):
    length = len(sequence)
    if length <= 1:
        return sequence
    else:
        pivot = sequence.pop()

    items_greater = []
    items_lower = []

    for item in sequence:
        if item > pivot:
            items_greater.append(item)

        else:
            items_lower.append(item)

    return quick_sort(items_lower) + [pivot] + quick_sort(items_greater)

print(quick_sort([5,6,7,8,9,8,7,6,5,6,7,8,9,0]))
```

Picking a good pivot point will significatly reduce it's time complexity. 

Worst case scenario, we are looking at O(n²) but best case scenario is O(nlogn). 
