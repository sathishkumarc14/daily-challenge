# daily-challenge
# Two Sum

## Problem Statement
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

## Approach
- Use a hash map to store the indices of the elements.
- Iterate through the array and check if the complement (target - current element) exists in the hash map.
- If found, return the indices.

## Complexity Analysis
- Time Complexity: O(n)
- Space Complexity: O(n)

## Solution
```javascript
function twoSum(nums, target) {
    const numToIndex = new Map();
    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];
        if (numToIndex.has(complement)) {
            return [numToIndex.get(complement), i];
        }
        numToIndex.set(nums[i], i);
    }
}