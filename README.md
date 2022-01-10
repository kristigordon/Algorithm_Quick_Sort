# Algorithm_Quick_Sort

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
        # This allows us to simply return the sequence if its length is < 1, meaning 
        # there is nothing to compare the number to and it will be properly sorted. 
    else:
        pivot = sequence.pop()
        # For everything else we will use our pivot. 
        # To do so we pop the last number to use as the pivot number and then return 
        # that number after it has been iterated through. 

    items_greater = []
    items_lower = []
    # This gives us a list to store the elements that are less than our pivot point 
    # or greater than our pivot point. 

    for item in sequence:
        if item > pivot:
            items_greater.append(item)
            # This is allowing an item, if it is greater than the pivot, to be appended 
            #to or added to the items_greater list for us to use later.

        else:
            items_lower.append(item)
            # Same thing here, but if the item is less than our pivot point, it is added here. 

    return quick_sort(items_lower) + [pivot] + quick_sort(items_greater)
    # We then want to iterate thorugh this list again performing the quick sort on the 
    # items_lower and the items_greater.
    # This will run until we have the <= 1 len exception that we specified on our third line of code. 
    # The sequence will then be returned with everything sorted in ascending order. 

print(quick_sort([5,6,7,8,9,8,7,6,5,6,7,8,9,0]))
```

Picking a good pivot point will significatly reduce it's time complexity. 

Worst case scenario, we are looking at O(n²) but best case scenario is O(nlogn). 
