# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

![Screenshot 2023-12-27 182835](https://github.com/23005672/QRdecomposition/assets/138971519/83fd2842-3503-47e0-83fe-5e6c5eea7e86)


3.	Obtain the Q matrix   
![Screenshot 2023-12-27 182847](https://github.com/23005672/QRdecomposition/assets/138971519/44bc33f2-a95c-4e16-82fa-83ed2a7d2c3d)


4.	Construct the upper triangular matrix R
  ![Screenshot 2023-12-27 182908](https://github.com/23005672/QRdecomposition/assets/138971519/35e3f720-a7d4-41c0-b556-9c0db5fcfdb9)



## Program:
### Gram-Schmidt Method
```PYTHON
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: RIYA P L
RegisterNumber: 23005672
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(a[:,i]@Q[:,j]*Q[:,j])
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=a[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![qr](https://github.com/23005672/QRdecomposition/assets/138971519/f4054e71-330e-4811-ad3e-4a48a8064e28)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
