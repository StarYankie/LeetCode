## Problem

https://leetcode-cn.com/problems/two-sum

## Problem Description

```
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

## Code

- Support Language: Java

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map hashMap = new HashMap<>();
    	int[] sol = new int[2];
    	int tempIdx = -1, temp = -1;
    	for(int i=0;i<nums.length;i++) {
    		hashMap.put(i, nums[i]);
    	}
    	for(int i=0;i<nums.length;i++) {
    		if(hashMap.containsValue(target-nums[i])) {
    			sol[0] = i;
    			temp = target-nums[i];
    		}
    	}
    	for(Object o: hashMap.keySet()) {
    		if ((Integer)hashMap.get(o) == temp && (Integer)o != sol[0]) {
    			sol[1] = (Integer)o;
    		}
    	}
    	return sol;
    }
}
```