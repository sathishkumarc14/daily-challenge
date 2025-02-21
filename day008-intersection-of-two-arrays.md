
# Day 08 - Intersection of Two Arrays

## Problem Statement
Given two integer arrays nums1 and nums2, return an array of their 
intersection
. Each element in the result must be unique and you may return the result in any order.

## Example 1:
Input: `nums1 = [1,2,2,1], nums2 = [2,2]`  
Output: `[2]`

## Approach 1: Brute force
1. Initialize empty array to get the unique elements
2. Itrate over any one of given array
3. If the element is found second array and not found unique array then add element into new array
```javascript
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersection = function(nums1, nums2) {
    var unique = [];
    for(let i = 0; i < nums1.length; i++){
        if(nums2.indexOf(nums1[i]) > -1){
            if(unique.indexOf(nums1[i]) == -1)
                unique.push(nums1[i]);
        }
    }
    return unique;
};
```
## Approach 2: 
```javascript

```
