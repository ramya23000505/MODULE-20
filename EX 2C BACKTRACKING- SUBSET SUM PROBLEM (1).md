# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start the program.

2. Take the number of elements n and the list of n integers as input, followed by the target sum x.

3. Use combinations from the itertools library to generate all possible subsets of the list.

4. For each subset, check if the sum of its elements equals x.

5. If the sum matches, print the subset.

6. Continue until all subsets are checked.

7. If no subset is found with the sum x, no output is produced.   

8. End of program

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: RAMYA R
Register Number:  212223230169
*/

from itertools import combinations

def subsetSum(n, arr, x):
	for i in range(n+1):
		for subset in combinations(arr, i):
			if sum(subset) == x:
				print(list(subset))


n=int(input())
arr=[]
for i in range(0,n):
    a=int(input())
    arr.append(a)
x = int(input())

subsetSum(n, arr, x)

```

## Output:
![image](https://github.com/user-attachments/assets/be162a42-860c-4942-b849-e7328e6a6672)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
