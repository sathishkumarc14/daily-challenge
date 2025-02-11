
# Day 02 - Best Time to Buy and Sell Stock

## Problem Statement
You are given an array prices where `prices[i]` is the price of a given stock on the `ith` day.
You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return `0`.

Example 1:

Input: prices = `[7,1,5,3,6,4]`  
Output: `5`  
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.


## Approach 1: Brute Force 1
It's getting "Time Limit Exceeded" response while submitting it.
```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    var pricesLength = prices.length;
    var maxProfit = 0;
    for(let i = 0; i < pricesLength; i++){  
        for(let j = i + 1; j < pricesLength; j++){
            var profit = prices[j] - prices[i];
            maxProfit = Math.max(maxProfit, profit);
        }
    }
    return maxProfit;
}
```
## Approach 2: Brute Force 2
```javascript
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    var pricesLength = prices.length;
    var minPrice = 1/0;
    var maxProfit = 0;
    for(let i = 0; i < pricesLength; i++){  
        if (minPrice > prices[i]) {
            minPrice = prices[i];
        } else if ((prices[i] - minPrice) > maxProfit) {
            maxProfit = prices[i] - minPrice;
        }        
    }
    return maxProfit;
}  
```