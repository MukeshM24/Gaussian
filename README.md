# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### 1 Gaussian Elimination (No Pivoting): Zero below diagonal, then solve bottom-up.
### 2. Gaussian Elimination (With Pivoting): Pick largest row value, zero below diagonal, solve bottom-up.
### 3. Gauss-Jordan Elimination: Zero above and below diagonal, then divide by diagonal.
### 4. LU Decomposition: Split into lower and upper parts, solve forward then backward.



## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Mukesh M
Register No:26013543
'''                    
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j  in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
         sys.exit("Divide by zero detected")
    for j in  range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n] /a [n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i] - a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
     print("X%d = %.2f"%(i,x[i]),end =' ' )

```

## Output:
<img width="1238" height="657" alt="image" src="https://github.com/user-attachments/assets/d34e9777-d197-40de-a6cc-b2a942e9592e" />
<img width="1275" height="523" alt="image" src="https://github.com/user-attachments/assets/ab7de791-0efc-4b2c-8bb5-c879a03373c8" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

