# Start Here
**Problem Code:** CF5  
**Problem Link:** https://www.codechef.com/CSEP2017/problems/CF5

## Problem Description
This is a fairly easy question, the input contains of a list of numbers and you have to find out if there exists a number in the list such that sum of the elements on its left = sum of the elements on its right.

## Input
The first line of the input contains an integer T denoting the number of test cases.
The first line of each test case contains a single integer N denoting the number of integers in the list. The second line contains N space-separated integers

## Output
For each test case, print Yes if it has a number whose Sum(left)=sum(right) and No if it doesn't have such a number.

## Constraints
* 1 ≤ T ≤ 100
* 1 ≤ N ≤ 10^5
* 1 ≤ integer of the list ≤ 10^5

## Example
```
Input:
2
3
1 2 3
4
1 2 3 3

Output:
No
Yes
```

## Code (C)
```
#include <stdio.h>

int main(void) {
	int tc, i, n, j, num[1000], k, left, right, flag;

	scanf("%d", &tc);

	for (i = 0; i < tc; i++) {
			flag = 0;

	    scanf("%d", &n);

	    for (j = 0; j < n; j++) {
	        scanf("%d", &num[j]);
	    }

	    for (j = 1; j < n-1; j++) {
					left = 0; right = 0;

	        for (k = 0; k < j; k++) {
	            left += num[k];
	        }
	        for (k = j+1; k <= n; k++) {
	            right += num[k];
	        }

	        if (left == right) {
	            flag = 1;
	        }
	    }

			if (flag == 1)
					printf("Yes\n");
			else
					printf("No\n");
	}

	return 0;
}
```
