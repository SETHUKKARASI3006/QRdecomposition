# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![image](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/fff183d2-3d75-4e67-a64f-6c62b8a46a2e)

    ![image](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/43e44ff2-e5e2-49f4-ac81-01ca906505ac)

    ![image](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/0d9dbb18-6735-419a-b78f-d1f8cd67e860)

3.	Obtain the Q matrix   
    ![image](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/f2d965b1-0904-4c90-9b25-a77cb9043012)

4.	Construct the upper triangular matrix R
    ![image](https://github.com/SETHUKKARASI3006/QRdecomposition/assets/144979338/34516581-2f68-4987-8663-9d69e5c93218)



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
