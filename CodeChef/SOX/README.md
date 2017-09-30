# XOR
## Problem Code: SOX
Contest URL: https://www.codechef.com/CSEP2017/problems/SOX

### Problem Description
0<=x<=n
n+x=n^r
where ^ denotes the bitwise XOR operator. Then print an integer denoting the total number of x's satisfying the criteria above.

### Input
An integer n

### Output
Print the total number of X found

### Constraints
* 1 <= N <= 10 ^ 15

### Example
```
Input:
5

Output:
2
```

### Code (Python 2.7)
```
n = int(input())
c = 0
for x in xrange(n+1):
	if (n+x == n^x):
		c = c + 1
print c
```
