
# Day 05 - Reverse Linked List

## Problem Statement
Given the `head` of a singly linked list, reverse the list, and return the reversed list.

## Example 1:
Input: `head = [1,2,3,4,5]`
Output: `[5,4,3,2,1]`

## Approach 1: Brute force
1. Traverse through linked list to get all values
2. Put all values into empty array
3. Itrate from last index of the array
4. Create new linked list thorugh array itration
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    var arr = [];
    var cur = head;
    while(cur){
        arr.push(cur.val)
        cur = cur.next
    }

    var reverse = new ListNode();
    var pointer = reverse;
    for(let i = arr.length; i >= 0; i--){
        pointer.next = new ListNode(arr[i]);
        pointer = pointer.next;
    }
    return reverse.next.next;
};
```
## Approach 2: 
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    var arr = [];
    var cur = head;
    while(cur){
        arr.push(cur.val)
        cur = cur.next
    }

    var reverse = new ListNode();
    var pointer = reverse;
    while(arr.length > 0){
        pointer.next = new ListNode(arr.pop());
        pointer = pointer.next; 
    }
    return reverse.next;
};
```