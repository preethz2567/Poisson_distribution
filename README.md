# EXP-02
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
### DEVELOPED BY : PREETHI D
### REG NO : 212224040250
```
  import numpy as np
  import math
  import matplotlib.pyplot as plt
  x=[ int(i) for i in input().split()]
  y=[ int(i) for i in input().split()]
  N=len(x)
  Sx=0
  Sy=0
  Sxy=0
  Sx2=0
  Sy2=0
  for i in range(0,N):
      Sx=Sx+x[i]
      Sy=Sy+y[i]
      Sxy=Sxy+x[i]*y[i]
      Sx2=Sx2+x[i]**2
      Sy2=Sy2+y[i]**2
  r=(N*Sxy-Sx*Sy)/(math.sqrt(N*Sx2-Sx**2)*math.sqrt(N*Sy2-Sy**2))
  print("The Correlation coefficient is %0.3f"%r)
  byx=(N*Sxy-Sx*Sy)/(N*Sx2-Sx**2)
  xmean=Sx/N
  ymean=Sy/N
  print("The Regression line Y on X is ::: y = %0.3f + %0.3f (x-%0.3f)"%(ymean,byx,xmean))
  plt.scatter(x,y)
  def Reg(x):
    return ymean + byx*(x-xmean)
  x=np.linspace(20,80,51)
  y1=Reg(x)
  plt.plot(x,y1,'r')
  plt.xlabel('x-data')
  plt.ylabel('y-data')
  plt.legend(['Regression Line','Data points'])
 
```
# Output : 
![image](https://github.com/user-attachments/assets/caa2fc3c-ceaa-4616-841e-5f9a5d54427b)



# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
