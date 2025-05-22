# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:16/5/25
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1.Get the input array: Take the array elements from the user and store them in a list.

2.Define the target: Take the target sum that we need to check if a subset exists.

3.Recursive function: Use a recursive function (SubsetSum) to explore all possible subsets, checking if any subset's sum equals the target.

4.Backtracking: The function checks both possibilities for each element: including it in the subset or excluding it.

5.Print result: If a subset with the given sum is found, print "True, subset found"; otherwise, print "False, subset not found".   

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def SubsetSum(a,i,sum,target,n):
    if i == n:
        return sum == target
    if sum>target:
        return False
    if sum == target:
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```
## Output:

![image](https://github.com/user-attachments/assets/02d713cf-1004-41dd-82dc-79613df8d0e8)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
