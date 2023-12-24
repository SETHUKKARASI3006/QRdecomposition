# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.png)

    ![eqn2](./ex6.png)

    ![eqn3](./ex3.png)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.png)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.png)



## Program:
### Gram-Schmidt Method
```


''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: SETHUKKARASI C
RegisterNumber: 23012881
'''
import numpy as np
def QR_Decomposition(A):
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)




```

## Output

![output](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/3ed49ac6-9b3e-49b7-af78-67df3d00e120)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
