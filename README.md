# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:


Program to QR decomposition using the Gram-Schmidt method


Developed by: Subashini K

RegisterNumber: 212225240160
```

import numpy as np

def QR_Decomposition(A):

 n,m=A.shape
 
 Q=np.zeros((n,n))
 
 u=np.zeros((n,n)) 
 
 u[:, 0]=A[:, 0]
 
 Q[:, 0]=u[:, 0]/np.linalg.norm(u[:, 0])
 
 for i in range(1,n):
 
   u[:, i]=A[:, i]
   
   for j in range(i):
   
      proj=np.dot(A[:, i],Q[:, j])
      
      u[:, i]=(u[:, i]-proj*Q[:, j])
  
   Q[:   , i]=u[:, i]/np.linalg.norm(u[:, i])

 R=np.zeros((n,m))
 
 for i in range(n):
 
    for j in range(i,m):
    
        R[i,j]=np.dot(Q[:, i], A[:, j])

 np.set_printoptions(suppress=True)
 
 
 print("The Q Matrix is")
 
 print("",Q)
 
 print("The R Matrix is")
 
 print("",R)

data=eval(input())

if isinstance(data,tuple):

    data=data[0]

A=np.array(data)

QR_Decomposition(A)
```


## Output

<img width="1920" height="1080" alt="Screenshot (205)" src="https://github.com/user-attachments/assets/459e4c4c-3037-40cb-9da6-85b14298b239" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
