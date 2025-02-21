
# Day 09 - Linked List Cycle

## Problem Statement
Given head, the `head` of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the `next` pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return `true` if there is a cycle in the linked list. Otherwise, return `false`.
## Example 1:
![Alt text](day009-example.png)  
Input: `head = [3,2,0,-4], pos = 1`
Output: `true`
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

## Approach 1: Brute force
1. Initialize a `Set` 
2. Iterate over linked list and put it into Set valriable
3. On subsequent iteration if the same node is available in `Set` then return `true` else `false`
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
## Approach 2: Floyd's Cycle-Finding Algorithm (Tortoise and Hare) algorithm
## Concept
Uses two pointers moving at different speeds to identify cycles.
## Initialization
- `slow` pointer moves one step at a time.
- `fast` pointer moves two steps at a time.
## Traversal
- In each iteration, move the `slow` pointer by one step.
- Move the `fast` pointer by two steps.
## Cycle Detection
- If `slow` and `fast` pointers meet, a cycle exists.
- If `fast` reaches the end of the list (`null`), there is no cycle.

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
    if(head == null)
        return false;
    var slow = head;
    var fast = head.next;
    while(fast != null && fast.next != null){
        if(slow == fast){
            return true;
        }
        var slow = slow.next;
        var fast = fast.next.next;
    }
    return false;
};
```
