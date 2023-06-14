# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Gaussian elimination is a method for solving matrix equations of the form AX=b
2. To perform Gaussian elimination starting with the system of equations
3. Compose the "augmented matrix equation"
4. Here, the column vector in the variables X is carried along for labeling the matrix rows.
Now, perform elementary row operations to put the augmented matrix into the upper triangular form
5.  Solve the equation of the th row for , then substitute back into the equation of the (k-1)st row to
obtain a solution for Xk-1, etc., according to the formula
## Program:
```
'''Program to solve a matrix using Gaussian elimination with partial pivoting.
Developed by: shalini.k
RegisterNumber: 212222240095
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=' ')

```

## Output:

![image](https://github.com/shalinikannan23/Gaussian/assets/118656529/99d40bc9-b0c7-4689-9dd2-2a328ad3912e)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

