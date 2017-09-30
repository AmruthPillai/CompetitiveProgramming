# Game
**Problem Code:** GME  
**Problem Link:** https://www.codechef.com/CSEP2017/problems/GME

## Problem Description
Louise and Richard play a game. They have a counter set to N. In every game, Louise gets the first turn and the turns alternate thereafter. In the game, they perform the following operations. If N is not a power of 2 , reduce the counter by the largest power of 2 less than N . If N is a power of 2 , reduce the counter by half of N . The resultant value is the new N which is again used for subsequent operations. The game ends when the counter reduces to 1, i.e.,N is equal to 1 , and the last person to make a valid move wins. Given N, your task is to find the winner of the game. If N is 1, Richard Wins.  

## Input
The first line of the input contains an integer T denoting the number of test cases.The subsequent lines each contain an integer N , the initial number set in the counter.

## Output
For each test case, print the winner's name in a new line. So if Louise wins the game, print "Louise". Otherwise, print "Richard". (Quotes are for clarity).

## Constraints
* 1 <= T <= 10
* 1 <= N <= 2^64-1

## Example
```
Input:
1
6

Output:
Richard
```

## Code (Java 8)
```
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
import java.lang.*;

public class Main {
    public static void find_winner(BigInteger N) {
        String winner = "Richard";
        if (N.equals(BigInteger.valueOf(1))) {
            System.out.println(winner);
        } else {
        	// convert N to binary. It's a given that this binary number starts with 1.
        	String binary_N = N.toString(2);
            winner = "Louise";
            while (true) {
                // if N is a power of 2, divide by 2 i.e. shift number 1 place right
                // if N is not a power of 2, subtract from largest power of 2 i.e. the leftmost 1
                // always check if N is 1 at the end
            	int first_one = binary_N.indexOf("1", 1);
            	if (first_one == -1) {		// N is power of 2 (is in the form of 100...0)
            		binary_N = binary_N.substring(0, binary_N.length()-1);
            		if (binary_N.equals("1")) {
            			System.out.println(winner);
            			break;
            		} else {
            			winner = flip_winner(winner);
            		}
            	} else {					// N is not power of 2
            		binary_N = binary_N.substring(first_one);
            		if (binary_N.equals("1")) {
            			System.out.println(winner);
            			break;
            		} else {
            			winner = flip_winner(winner);
            		}
            	}
            }


        }
    }

    public static String flip_winner(String winner){
        if (winner == "Richard"){
            return "Louise";
        } else {
            return "Richard";
        }      
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int number_of_tests = sc.nextInt();
        for (int i=0; i<number_of_tests; i++) {
            find_winner(sc.nextBigInteger());
        }
    }
}
```
