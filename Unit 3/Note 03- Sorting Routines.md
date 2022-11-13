## Note – Sorting Routines

**Sorting** is the process of putting items in a logical order, either from smallest to largest (ascending order), or largest to smallest (descending order). By default, when an array is sorted, we can assume it's in ascending order unless otherwise specified.

There are dozens of sorting algorithms commonly known. Here are visualizations of some common sorting algorithms: [15 Sorting Algorithms in 6 Minutes](https://www.youtube.com/watch?v=kPRA0W1kECg).

Here is another video on sorting algorithms: [Sorting Out Sorting](https://www.youtube.com/watch?v=SJwEwA5gOkM). This one was made in 1980 and is a classic. It's worth watching just for the retro sound effects. There is a short recap at the end if you don't want to watch the whole thing.

The following four sorting algorithms will be discussed in more detail this lesson. 
* Merge Sort
* Quick Sort
* Selection Sort
* Bubble Sort

You won't be expected to memorize which one is which, but you are expected to be able to follow the instructions and apply the algorithm. 

If you are interested, additional sorting algorithms are discussed in more detail in the optional note provided at the end of this unit. 
* Gnome Sort
* Shaker Sort
* Shell Sort
* Insertion Sort
* Comb Sort
* Bogo Sort

They will be described using **pseudocode**, which is a combination of code and plain English. There are usually several variations for each sorting algorithm -- this lesson only has one variation for each sorting algorithm.

**Bubble Sort**

```
Let the index be 0
Do the following until the array is sorted:
    Do the following until the index+1 is beyond the length of the array:
        If the element at the index is greater than the one after it:
            Swap them
        Increase the index by 1
```

The idea is that you have a bubble around two elements at a time. The bubble starts at the first two elements. If the elements in the bubble are not in order, they are swapped. The bubble then moves on to the second two elements. Again, it swaps the elements if they are not in order. It repeats this process until it reaches the end, then it goes back to the beginning and repeats the entire process over and over again until the entire array is sorted.

Here is a flowchart for the Bubble Sort algorithm:

![Bubble Sort](../Images/Bubble_Sort_Flowchart.png)

**Selection Sort**

```
Let index be 0
Do the following until the array is sorted:
    Find the lowest element between the index and the end of the array
    Swap the lowest element with the one at the index
    Increase the index by 1
```

The idea is that after `n` iterations, the element that belongs in the nth spot is swapped in order to put it in its correct place. The process continues until all the elements are in their correct place.

Here is a flowchart for the Selection Sort algorithm:

![Selection Sort](../Images/Selection_Sort_Flowchart.png)

### Better Sorting Algorithms

Selection and Bubble classified as inefficient sorting algorithms . They are relatively simple to understand, but they do more comparisons and/or swaps than necessary. Merge Sort and Quick Sort are among the most efficient sorting algorithms, but they are more difficult to code.

**Merge Sort**

```
Split the array into groups of 1
Do the following until all the elements are merged:
    For each pair of groups:
        Merge them into a new sorted group
```

The merging phase is the following.

```
Do the following until the two groups are merged into one group:
    Compare the first elements of the two groups
    Take the smaller one, remove it, and put it at the back of the new group
```

Here is an example of what merging two groups of two can look like.

![](../Images/Merge_Sort_Example.png)

In older versions of Java (before Java SE 7), the `sort()` method in the `Arrays` class uses Merge Sort when the array is composed of a primitive data type.

**Quick Sort**

```
Let the pivot be the first element
Let the leftIndex be 1 and the rightIndex be the last index of the array
Do the following until the leftIndex is equal to or greater than the rightIndex:
    If the leftIndex is more than the pivot and the rightIndex is less than the pivot:
        Swap them
        Increase the leftIndex by one
        Decrease the rightIndex by one
    If the leftIndex is less than the pivot:
        Increase the leftIndex by one
    If the rightIndex is more than the pivot:
        Decrease the rightIndex by one
If the leftIndex is greater than the rightIndex:
    Move the pivot in between leftIndex and the rightIndex
If the leftIndex is equal to the rightIndex:
    Move the pivot to the leftIndex/rightIndex
```

After one iteration of Quick Sort, all the elements to the right of the pivot are greater than it, and all the elements to the right of it are less than it.

This process is repeated on the two smaller arrays until the entire array is sorted.

Here is an example of one iteration of Quick Sort on a small array.

![](../Images/Quick_Sort_Example.png)

At the end of the iteration, 3 is in the correct location. The process can be repeated on the green array and on the cyan array.

In older versions of Java (before Java SE 7), the `sort()` method in the `Arrays` class uses Quick Sort when the array is composed of composite data type. The newest versions of Java uses Tim Sort (named after someone whose first name is Tim), which is a hybrid of Quick Sort and Insertion Sort.

### Stability of Sorting Algorithms

The **stability** of a sorting algorithm refers to whether it preserves the order of duplicate elements. A sorting algorithm is **stable** if it preserves the order of duplicate elements, and **unstable** otherwise.

This may seem unimportant, but when an array consists of objects, it is often desirable to preserve the order of objects with the same key (the attribute that is being sorted).

| Stable Sorting Algorithms | Unstable Sorting Algorithms |
| --- | --- |
| <ul><li>Gnome Sort</li><li>Bubble Sort</li><li>Shaker Sort</li><li>Insertion Sort</li><li>Merge Sort</li></ul> | <ul><li>Selection Sort</li><li>Shell Sort</li><li>Comb Sort</li><li>Bogo Sort</li><li>Quick Sort</li></ul> |
