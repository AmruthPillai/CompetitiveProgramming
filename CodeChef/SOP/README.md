# Operation on String
**Problem Code:** SOP  
**Problem Link:** https://www.codechef.com/CSEP2017/problems/SOP

## Problem Description
You are given a string, in one operation, you have to delete any pair of adjacent letters with same value. For example, string "aabcc" would become either "aab" or "bcc" after operation. you have to reduce the string as much as possible. To do this, you will repeat the above operation as many times as it can be performed. Note: If the final string is empty, print Empty String .  

## Input
The input is a string containing characters.

## Output
Print the final string after performing operations on it.

## Example
```
Input:
abb

Output:
a
```

## Code (Python 2.7)
```
s = raw_input()
stack = []

for c in s:
    if stack and stack[-1] == c:
        stack.pop()
    else:
        stack.append(c)

print ''.join(stack) if stack else 'Empty String'
```
