---
tags:
---
## Introduction

The two-way merge sort algorithm is a divide-and-conquer algorithm used to sort an array or list of elements in ascending or descending order. It follows the principle of breaking down the problem into smaller sub-problems, solving them recursively, and then combining the solutions to obtain the final sorted array.

The main purpose of the two-way merge sort algorithm is to efficiently sort a large array by dividing it into smaller sub-arrays, sorting them individually, and then merging them back together in a sorted manner. This algorithm has a time complexity of O(n log n), which makes it efficient for sorting large datasets.

## Algorithm

The two-way merge sort algorithm can be broken down into the following steps:

```
MERGE_SORT(arr, left, right)
    if left < right
        mid = (left + right) / 2
        MERGE_SORT(arr, left, mid)
        MERGE_SORT(arr, mid + 1, right)
        MERGE(arr, left, mid, right)

MERGE(arr, left, mid, right)
    i = left
    j = mid + 1
    k = 0
    temp = create a temporary array of size (right - left + 1)

    while i <= mid and j <= right
        if arr[i] <= arr[j]
            temp[k] = arr[i]
            i = i + 1
        else
            temp[k] = arr[j]
            j = j + 1
        k = k + 1

    while i <= mid
        temp[k] = arr[i]
        i = i + 1
        k = k + 1

    while j <= right
        temp[k] = arr[j]
        j = j + 1
        k = k + 1

    Copy the elements from temp back to arr
```

### Explanation

1. The `TWO_WAY_MERGE_SORT` function takes the array `arr`, and the left and right indices of the subarray to be sorted.
2. If the left index is less than the right index, it means there are at least two elements in the subarray.
3. The middle index `mid` is calculated to divide the subarray into two halves.
4. The function recursively calls itself with the left half (`left` to `mid`) and the right half (`mid + 1` to `right`) of the subarray.
5. After the recursive calls, the `MERGE` function is called to merge the two sorted subarrays into a single sorted subarray.
6. The `MERGE` function uses three indices: `i` for the left subarray, `j` for the right subarray, and `k` for the temporary array `temp`.
7. The elements from the left and right subarrays are compared and copied into the `temp` array in sorted order.
8. After merging, the elements from the `temp` array are copied back into the original array `arr`.

The two-way merge sort algorithm follows the divide-and-conquer approach, dividing the array into smaller subarrays, sorting them recursively, and then merging them back together in a sorted manner. This process continues until the entire array is sorted.