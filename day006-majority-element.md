
# Day 05 - Majority Element

## Problem Statement
Given an array `nums` of size `n`, return the majority element.

## Example 1:
Input: `nums = [3,2,3]`   
Output: `3`

## Approach 1: Brute force
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
## Approach 2: 
```javascript

```
