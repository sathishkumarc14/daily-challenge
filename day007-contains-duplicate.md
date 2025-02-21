# Day 07 - Contains Duplicate [217]

## Problem Statement
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

## Example 1:
Input: `nums = [1,2,3,1]`  
Output: `true`  
Explanation:  
The element `1` occurs at the indices `0 and 3`.  

## Approach 1: Brute force
1. Sort the given array
2. if two consecutive numbers are same then return `true` else `false` 
```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
    var sorted = nums.sort();
    var length = nums.length;
    for(let i = 0; i < length; i++){
        if((i < length - 1) && (nums[i] == nums[i+1])){
                return true;
        }
    }
    return false;
};
```
## Approach 2: 
1. Using `Set()` to find the dupicates
2. Itrate over the given array
3. Get the element from array check `Set` is having the same value then `true` else add new element in `Set`
```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
    var seen = new Set();
    var length = nums.length;
    for(let i = 0; i < length; i++){
        if(seen.has(nums[i])){
            return true;
        }else{
            seen.add(nums[i]);
        }
    }
    return false;
};
```
