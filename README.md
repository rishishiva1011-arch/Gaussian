# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import NumPy and sys module, then read the number of unknowns.
2. Take input values and form the augmented matrix (coefficients and constants together).
3. Apply forward elimination to convert the matrix into upper triangular form.
4. Perform back substitution to calculate the values of unknown variables.
5. Print the values of all variables.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Rishikesh S
RegisterNumber: 212225240118
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X{} = {:.2f}".format(i,x[i]),end=" ")
```

## Output:

<img width="588" height="350" alt="EXP-6" src="https://github.com/user-attachments/assets/bb2f7fcc-e933-4fd1-9215-34b8c4b73046" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

