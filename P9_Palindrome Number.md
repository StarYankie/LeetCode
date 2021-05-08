## Problem

https://leetcode.com/problems/palindrome-number/

## Problem Description

```
Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward. For example, 121 is palindrome while 123 is not.

```

## Code

- Support Language: Java

```java
class Solution {
    public boolean isPalindrome(int x) {
        String str = Integer.toString(x);
		for(int i=0;i<str.length()/2;i++) {
			if(str.charAt(i) != str.charAt(str.length()-i-1)) {
				return false;
			}
		}
		return true;
    }
}
```
