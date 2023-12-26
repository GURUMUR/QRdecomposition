# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

 ![image](https://github.com/GURUMUR/QRdecomposition/assets/144895197/51aa442d-54da-4f43-aec3-8b6b047ce804)

![image](https://github.com/GURUMUR/QRdecomposition/assets/144895197/99477d6e-7ecf-4431-a457-8c89d72947c7)

![image](https://github.com/GURUMUR/QRdecomposition/assets/144895197/9f600725-6007-4c2d-9a92-4a680289553c)


3.	Obtain the Q matrix   
![image](https://github.com/GURUMUR/QRdecomposition/assets/144895197/a0c86327-d73b-409e-beb2-d2d25f3814f7)

4.	Construct the upper triangular matrix R

![image](https://github.com/GURUMUR/QRdecomposition/assets/144895197/99477d6e-7ecf-4431-a457-8c89d72947c7)



## Program:
### Gram-Schmidt Method
```python

''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: GURUMURTHY S
RegisterNumber: 212223230066
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q = np.empty((n,m))
    u = np.empty((n,m))
    
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0]/np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i] -= (A[:,i] @ Q[:,j])*Q[:,j]
        
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
        
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
            
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)
```
## Output
![QR Decomposition](https://github.com/GURUMUR/QRdecomposition/assets/144895197/a99bc0a0-9b03-4cc7-bfe2-afbdb5bbee87)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
