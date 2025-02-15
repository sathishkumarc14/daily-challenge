
# Day 04 - Merge Two Sorted Lists

## Problem Statement
You are given the heads of two sorted linked lists list1 and list2.
Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.
Return the head of the merged linked list.

## Example 1:
Input: `list1 = [1,2,4], list2 = [1,3,4]`  
Output: `[1,1,2,3,4,4]`

## Approach 1: Linked List
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    var headNode = new ListNode(0);
    var current = headNode;
    while(list1 != null && list2 != null){
        if(list1.val < list2.val){
            current.next = list1;
            list1 = list1.next;
        }else{
            current.next = list2;
            list2 = list2.next;
        }
        current = current.next;
    }
    if(list1 != null)
        current.next = list1;
    if(list2 != null)
        current.next = list2;        
    return headNode.next;
};
```
## Approach 2: 
```javascript

```
