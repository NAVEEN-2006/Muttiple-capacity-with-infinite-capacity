# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)

### Developed by : NAVEEN KUMAR S
### Register number : 212223040129

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.


![image](https://github.com/NAVEEN-2006/Muttiple-capacity-with-infinite-capacity/assets/152067648/af3cc0b1-c36e-4058-a008-2beadb1559f9)



## Procedure :
![image](https://github.com/NAVEEN-2006/Muttiple-capacity-with-infinite-capacity/assets/152067648/e6be0252-0e6d-4351-aa0d-95d92b338e11)





## Experiment:
![image](https://github.com/NAVEEN-2006/Muttiple-capacity-with-infinite-capacity/assets/152067648/c2d10d6d-f920-4723-8446-572babdb4533)


![image](https://github.com/NAVEEN-2006/Muttiple-capacity-with-infinite-capacity/assets/152067648/0c501c17-bda6-4524-a293-9fa151f21978)



## Program :
```
import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
c=int(input("Number of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```

## Output :

![image](https://github.com/NAVEEN-2006/Muttiple-capacity-with-infinite-capacity/assets/152067648/aa97b376-305e-4e4a-b102-84758a2a93be)



## Result : 

Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
