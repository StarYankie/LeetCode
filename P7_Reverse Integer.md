## Problem

https://leetcode.com/problems/reverse-integer/

## Problem Description

```
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

```

## Code

- Support Language: Java

```java
class Solution {
    public int reverse(int x) {
        long temp = 0;
        String str = Integer.toString(x);
        String rStr = "";
        if (x >= 0) {
        	for(int i=str.length()-1;i>-1;i--) {
        	rStr += str.charAt(i);
        	}
        } else {
        	rStr += "-";
        	for(int i=str.length()-1;i>0;i--) {
            	rStr += str.charAt(i);
            }
        }
        temp = Long.parseLong(rStr);
        if(temp < Integer.MIN_VALUE || temp > Integer.MAX_VALUE) return 0;
        else return Integer.parseInt(rStr);
    }
}
```
