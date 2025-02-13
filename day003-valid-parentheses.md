
# Day 03 - Valid Parentheses

## Problem Statement
Given a string s containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

* Open brackets must be closed by the same type of brackets.
* Open brackets must be closed in the correct order.
* Every close bracket has a corresponding open bracket of the same type.

## Approach 1: Using Stack/Array
```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    var stack = [];
    for(let i = 0; i < s.length; i++){
        var c = s.charAt(i);
        if(c == "{"){
            stack.push("}");
        }else if(c == "("){
            stack.push(")");
        }else if(c == "["){
            stack.push("]");
        }else{
            if(stack.length == 0 || stack.pop() != c)
                return false;
        }
    }
    return (stack.length == 0)
};
```
## Approach 2: 
```javascript

```
