# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1. Start the program, import the required NumPy and Sys libraries, and get the order n of the matrix as input.

2. Initialize the augmented matrix a and solution array x with zeros. Read the augmented matrix elements from the user.

3. Perform Gaussian elimination to convert the augmented matrix into an upper triangular matrix. Check for zero diagonal elements to avoid division by zero, then use back substitution to calculate the unknown values.

4. Display the calculated values of the variables in the format X0, X1, ... up to two decimal places and Stop the program.

## Program:
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]= float(input())
for i in range(n):
    if a[i][i]== 0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio= a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]= a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]= a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %.02f '%(i,x[i]),end='')
```

## Output:


<img width="1907" height="907" alt="image" src="https://github.com/user-attachments/assets/1edbd3e5-ac25-40e9-959e-445bad16a6b3" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

