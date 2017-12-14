# Smartest Set

A smart-set is a set of distinct numbers in which all the elements have the same number of 1s in their binary form. The set of all smallest elements from each smart-set that can be formed from a given array of distinct positive numbers is known as the smartest-set.

So given an array of distinct numbers, outline the elements of the smartest-set in ascending sorted order.

---

### Example
Let the array be {6 , 2 , 11 , 1 , 9 , 14 , 13 , 4 , 18}.
In binary form the set is {110, 010, 1011, 0001, 1001, 1110, 1101, 0100, 10010}.
The smart-sets are {1, 2, 4}, {6, 9, 18}, {11, 13, 14}.

The smartest-set is {1,6,11} as each element is the smallest element from each smart-set.

### Input Format
The first line of input consists of an integer t. This is the number of test cases. For each test case, the first line of input contains an integer n. Here n is the number of elements in the array. The next line contains n space separated distinct integers which are the elements of the array.

### Output Format
The output will space separated integer elements of the smartest-set in ascending order.

### Constraints
0 < t < 1000 (This is the number of test cases
2 < n < 10000 (This is the number of integer elements of the array)
1 < Xi < 100000 (This is the size of each element of the array)

#### Sample Input:
```
3
9
6 2 11 1 9 14 13 4 18
3
7 3 1
3
1 2 4
```
#### Sample Output:
```
1 6 11
1 3 7
1
```

---

### Code (Python 2.x)
```
from collections import defaultdict

# Input Number of Test Cases
tc = input()

for i in xrange(tc):
    # Input Number of Elements in Set
    # (because of problem statement requirement)
    n = input()

    # Get User Input of the Set
    dumb_set = raw_input().split()

    # Converting string literals to integer
    dumb_set = map(int, dumb_set)

    # Sort the set according to ascending value
    dumb_set.sort()

    # Creating Binary Equivalent Set of the Dumb Set
    dumb_bin = []
    for x in dumb_set:
        dumb_bin.append(bin(x)[2:])

    # Create DefaultDict so we can store lists within dictionaries
    binary_dict = defaultdict(list)
    for x in dumb_bin:
        binary_dict[x.count('1')].append(x)

    # Print the smallest number from each smart set
    for x in binary_dict.keys():
        print(int(binary_dict[x][0], 2)),

    # Hack to move to the next line
    print ' '
```
