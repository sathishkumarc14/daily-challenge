
# Two Sum

## Problem Statement
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.


## Approach 1: Brute Force
```javascript
	/**
	 * @param {number[]} nums
	 * @param {number} target
	 * @return {number[]}
	 */
	var twoSum = function(nums, target) {
		var count = nums.length;
		var c = 0;
		for( ; c < count; c++){
			var fNUmber = nums[c];
			var d = c+1;
			for( ; d < count; d++){
				var sNUmber = nums[d]; 
				if((fNUmber + sNUmber) == target){
					return [c, d]
				}
			}
		}
	};
```
## Approach 2: Two-pass Hash Table
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const numToIndex = new Map();
    for (let i = 0; i < nums.length; i++) {
            const num = nums[i];
            const complement = target - num;
            
            if (numToIndex.has(complement)) {
                return [numToIndex.get(complement), i];
            }
            
            numToIndex.set(num, i);
        } 
};
```