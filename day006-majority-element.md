
# Day 05 - Majority Element

## Problem Statement
Given an array `nums` of size `n`, return the majority element.

## Example 1:
Input: `nums = [3,2,3]`   
Output: `3`

## Approach 1: Brute force
1. Iterate over given array of numbers
2. Initialize empty object, it holds the unique number and count of occurance
3. Update the object based on key and number of occurance
4. Iterate over object properties and identify the property of higher value
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
    var obj = {
    };
    for(let i = 0; i < nums.length; i++){
        var num = nums[i];
        if(Object.hasOwn(obj, num)){
            obj[num] = obj[num] + 1;
        }else{
            obj[num] = 1;
        }
    }
    var max = '';
    var maxVal = 0;
    for (var prop in obj) {
        if(maxVal < obj[prop]){
           max = prop;
           maxVal = obj[prop];
        }
    }  
    return Number(max);  
};
```
## Approach 2: Boyer-Moore Majority Voting Algorithm
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
    var candidate = 0;
    var count = 0;
    
    for(let i = 0; i < nums.length; i++){
        if(count == 0){
            candidate = nums[i];
        }
        if(candidate == nums[i]){
            count += 1;            
        } else {
            count -= 1;
        }
    }
    
    return candidate;
};

```
