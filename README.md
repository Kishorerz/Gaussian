# Gaussian Elimination
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm
1. import numpy and sys to use the built-in functions for calculation.
2. Get the size of the matrix (order) from the user and initialize an empty matrix and vector
3. Using for loop get elements of the matrix and vector from the user.
4. Using another for loop to take each element in the matrix and solve in row echloen form.
5. Perform back subsitution and print the values with two decimal places.
6. End the Program. 

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
![output](https://github.com/Kishorerz/Gaussian/assets/144451216/2213a38b-3c0d-4de1-aa29-5e34f5a755ad)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

