# Program Your Own Calculator

**Problem Code:** URCALC  
**Problem Link:** https://www.codechef.com/problems/URCALC

## Code (Python 3)
```python
a = int(input())
b = int(input())
c = input()

if c == '+':
	result = a + b
elif c == '-':
	result = a - b
elif c == '*':
	result = a * b
elif c == '/':
	result = a / b
	
print(result)
```
