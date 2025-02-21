
# Day 09 - Linked List Cycle

## Problem Statement
Given head, the `head` of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the `next` pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return `true` if there is a cycle in the linked list. Otherwise, return `false`.
## Example 1:
![Alt text](day009-example-1.png)  
Input: `head = [3,2,0,-4], pos = 1`
Output: `true`
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

## Approach 1: Brute force
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} head
 * @return {boolean}
 */
var hasCycle = function(head) {
    var visitedNode = new Set();
    var current = head;
    while(current != null){
        var temp = current.next;
        if(visitedNode.has(temp)){
            return true;
        }else{
            visitedNode.add(temp);
        }
        current = temp
    }
    return false;
};

```
## Approach 2: 
```javascript

```
