# A Balanced Contest

**Problem Code:** PERFCONT  
**Problem Link:** https://www.codechef.com/OCT17/problems/PERFCONT

## Code (Python 2.7)
```
tc = int(raw_input())

for i in xrange(tc):
    balance = [0,0]

    problems, participants = map(int, raw_input().split())
    numbers = map(int, raw_input().split())

    cake_th = participants / 2
    hard_th = participants / 10

    for i in numbers:
        if (i >= cake_th):
            balance[0] = balance[0] + 1
        elif (i <= hard_th):
            balance[1] = balance[1] + 1

    if (balance[0] == 1 and balance[1] == 2):
        print 'yes'
    else:
        print 'no'
```
