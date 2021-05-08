## Problem

https://leetcode.com/problems/add-two-numbers/

## Problem Description

```
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

```

## Code

- Support Language: Java

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dh = new ListNode(0);
		ListNode curr = dh;
		ListNode p = l1;
		ListNode q = l2;
		int carry = 0;

		while(p != null || q != null) {
			int a = (p != null) ? p.val : 0;
            int b = (q != null) ? q.val : 0;
            int sum = a + b + carry;
			carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if( p != null ) p = p.next;
            if( q != null ) q = q.next;
		}
        if (carry > 0){
            curr.next = new ListNode(carry);
        }
        return dh.next;
    }
}
```
