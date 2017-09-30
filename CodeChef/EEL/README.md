# Politicians and Businessmen
**Problem Code:** EEL  
**Problem Link:** https://www.codechef.com/CSEP2017/problems/EEL

## Problem Description
Big Politicians and Businessmen are attending an event today. All of them have been given their Bank Balances as their Unique IDs.
Your Job is to provide them entry to the Event Arena in such a manner that Politicians/Businessmen with bigger Unique IDs are to be put first in the Entry Queue, followed by the lower ones.
Politicians/Businessmen with equal Unique IDs are to be placed in the Queue one after the other.

## Input
The first line contains an integer n, denoting the number of Unique IDs in an unsorted manner.
Each of the n subsequent lines, contains the Unique ID.

## Output
Print the sequence of the queue with each Unique Id in a separate line, in reverse order.

## Constraints
* 1 <= N <= 1000000
* 1 <= Unique ID <= 10^18

## Example
```
Input:
4
10000
30000
60000
5000

Output:
5000
10000
30000
60000
```

## Code (Python 2.7)
```
tc = int(raw_input())

n = []

for i in range(tc):
  n.append(int(raw_input()))

for i in sorted(n):
	print i
```
