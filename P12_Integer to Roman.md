## Problem

https://leetcode.com/problems/integer-to-roman/

## Problem Description

```
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

```

## Code

- Support Language: Java

```java
class Solution {
    public String intToRoman(int num) {
        int n1 = 0, n2 = 0, n3 = 0, n4 = 0;
    	String s1 = "", s2 = "", s3 = "", s4 = "";
    	
    	n1 = num / 1000;
    	num = num % 1000;
    	n2 = num / 100;
    	num = num % 100;
    	n3 = num / 10;
    	num = num % 10;
    	n4 = num;
    	
    	// 천의 자리
    	for(int i=0;i<n1;i++) {
    		s1 += "M";
    	}
    	
    	// 백의 자리
    	if(n2 <= 3) {
    		for(int i=0;i<n2;i++) {
        		s2 += "C";
        	}
    	} else if (n2 == 4)  {
    		s2 = "CD";
    	} else if (n2 > 4 && n2 <9) {
    		s2 += "D";
    		for(int i=5;i<n2;i++) {
    			s2 += "C";
        	}
    	} else {
    		s2 = "CM";
    	}
    	
    	// 십의 자리
    	if(n3 <= 3) {
    		for(int i=0;i<n3;i++) {
        		s3 += "X";
        	}
    	} else if (n3 == 4)  {
    		s3 = "XL";
    	} else if (n3 > 4 && n3 <9) {
    		s3 += "L";
    		for(int i=5;i<n3;i++) {
    			s3 += "X";
        	}
    	} else {
    		s3 = "XC";
    	}
    	
    	// 일의 자리
    	if(n4 <= 3) {
    		for(int i=0;i<n4;i++) {
        		s4 += "I";
        	}
    	} else if (n4 == 4)  {
    		s4 = "IV";
    	} else if (n4 > 4 && n4 <9) {
    		s4 += "V";
    		for(int i=5;i<n4;i++) {
    			s4 += "I";
        	}
    	} else {
    		s4 = "IX";
    	}
        return s1 + s2 + s3 + s4;
    }
}
```
