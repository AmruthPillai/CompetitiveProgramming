# Roots of a Quadratic Equation

https://www.codechef.com/problems/QUADROOT

Code (Python 3)
```python
import math

a = int(input())
b = int(input())
c = int(input())

x1 = (-1 * b + math.sqrt(b * b - 4 * a * c))/(2 * a)
x2 = (-1 * b - math.sqrt(b * b - 4 * a * c))/(2 * a)

print(x1)
print(x2)
```
