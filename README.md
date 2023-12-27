# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :
Developed By: EASWAR R

Register No: 23012868

import numpy as np.    
import math      
import scipy.stats      
L=[int(i) for i in input().split()]     
N=len(L); M=max(L)     
X=list();f=list()     
for i in range (M+1):     

    c = 0      
    for j in range(N):    
         if L[j]==1:     
         c=c+1     
    f.append(c)     
    X.append(1)     
sf=np.sum(f)         
p=list()     
for i in range(M+1):  

    p.append(f[i]/sf)     
mean=np.inner(X,p)     
p=list();E=list(); xi-list()      
print("X P(X=x) Obs. Fr Exp.Fr xi")      
print("---------------------------")      
for x in range(M+1):       

    p.append(math.exp(-mean)mean*x/math.factorial(x))      
    E.append(p[x]*sf)      
    xi.append((f[x]-E[x])**2/E[x])     
    print("%2.2f %2.3F %4.2f %3.2f %3.2f"%(x,p[x], f[x], E[x], xi[x]))      
print("----------------------------")       
cal_chi2_sq=np.sum(xi)      
print("Calculated value of Chi square is %4.2f"%cal_chi2_sq)      
table_chi2=scipy.stats.chi2.ppf(1-.81,df=M)      

print("Table value of chỉ square at 1 level is %4.2f"%table_chi2)      
if cal_chi2_sq<table_chi2:   

     print("The given data can be fitted in poisson Distribution at 1% LOS")  

else:     

     print("The given data cannot be fitted in Poisson Distribution at 1% LOS")      


# Output : 
50 14 23 7 3 5 7 7 2 3 3 5 3 61    
X P(X=x) Obs. Fr Exp.Fr xi    
-------------------------
0.00 0.024 1.00 0.44 0.73     
1.00 0.090 2.00 1.62 0.09    
2.00 0.168 2.00 3.02 0.34    
3.00 0.208 5.00 3.74 0.42    
4.00 0.193 1.00 3.48 1.77    
5.00 0.144 3.00 2.59 0.06   
6.00 0.089 1.00 1.61 0.23     
7.00 0.047 3.00 0.85 5.38  
-------------------------
Calculated value of Chi square is 9.03    
Table value of chi square at 1 level is 18.48     
The given data can be fitted in poisson Distribution at 1% LOS    


# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
