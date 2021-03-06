## Problem

https://leetcode.com/problems/remove-duplicates-from-sorted-array/

## Problem Description

```
Given a sorted array nums, remove the duplicates in-place such that each element appears only once and returns the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by reference, which means a modification to the input array will be known to the caller as well.

Internally you can think of this:

// nums is passed in by reference. (i.e., without making a copy)
int len = removeDuplicates(nums);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}

```

## Code

- Support Language: Java

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int size = 0;
        int cursor = 0;
        int cursor2 = 1;
        for (int i : nums) {
            if (cursor == 0) {
                size++;
            } else {
                if (nums[cursor - 1] < nums[cursor]) {
                    nums[cursor2++] = i;
                    size++;
                }
            }
            cursor++;
        }
        return size;
    }
}
```
