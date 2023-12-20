# Gaussian Elimination
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm
import numpy and sys to use the built-in functions for calculation.
Get the size of the matrix (order) from the user and initialize an empty matrix and vector
Using for loop get elements of the matrix and vector from the user.
Using another for loop to take each element in the matrix and solve in row echloen form.
Perform back subsitution and print the values with two decimal places.
End the Program. 

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: KISHOR KUMAR B.
RegisterNumber: 23009985
'''
import sys
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range (n):
    if matrix[i][i]==0.0:
        sys.exit('Divide by zero error')
    for j in range (i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range (n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#  back substitution
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range (i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range (n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")

```

## Output:
![gaussian elimination](./Screenshot%202023-12-20%20232649.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

