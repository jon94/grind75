# grind75

## Problem 1
Date: 27th April 2022
```
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.
```
Example 1:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```
Example 2:
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```
Example 3:
```
Input: nums = [3,3], target = 6
Output: [0,1]
```
Solution
```python
class Solution:
  def twoSum (self, nums: List[int], target: int) -> List[int]:
    for i in range(len(nums)):
      for j in range(i+1,len(nums)):
        if target == nums[j]+nums[i]:
          return [i,j]
```
 
 ## Problem 2
 Date: 27th April 2022
```
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
An input string is valid if:
Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
```
Example 1:
```
Input: s = "()"
Output: true
```
Example 2:
```
Input: s = "()[]{}"
Output: true
```
Example 3:
```
Input: s = "(]"
Output: false
```
Solution:
```python 
class Solution:
  def isValid(self, s:str) -> bool:
    stack=[]
    closetoOpen = {")":"(", "]":"[", "}":"{"} #Key value pair of close to open parenthese
    
    for c in s:
      if c in closetoOpen:
        if stack and stack[-1] == closetoOpen[c]: #if any of close bracket matches value (open bracket)
          stack.pop()
        else
          return False
      else
        stack.append(c)
    return True if not stack else False #can only return true if stack is empty.     
```
