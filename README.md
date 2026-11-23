# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start and read the order of the matrix  and the augmented matrix .
2. Perform forward elimination to convert the matrix into an upper triangular matrix. Check for zero diagonal elements.
3. Use back substitution to calculate the values of the unknown variables.
4. Display the values of all unknown variables and stop

## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: DAKSHA C
RegisterNumber: 212224230048
```
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')
```

## Output:
<img width="445" height="837" alt="Screenshot 2026-11-23 104133" src="https://github.com/user-attachments/assets/635c3ead-4a87-4d43-a7af-9bffc2976fdb" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

