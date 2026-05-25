# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Procedure :
![image](https://user-images.githubusercontent.com/103921593/203238265-176740b0-eae2-4772-90be-5449869ac9b0.png)
## Experiment:
## Program
```
arr_time_input = '' 
while not arr_time_input.strip(): # Loop until a non-empty input is received 
   arr_time_input = input("Enter the mean inter arrival time of objects from feeder (in 
secs):") 
   if not arr_time_input.strip(): 
       print("Input cannot be empty. Please enter a value.") 
arr_time = float(arr_time_input) 
ser_time=float(input("Enter the mean inter service time of lathe machine (in secs):")) 
Robot_time=float(input("Enter the Additional time taken for the robot (in secs):")) 
c=int(input("Number of service centres:")) 
lam=1/arr_time 
mu=1/(ser_time+Robot_time) 
print("------------------------------------------------") 
print("Multiple Server with infinite capacity- (M/M/c):(00/FIFO)") 
print("----------------------------------------------------") 
print("The mean arrival rate per second: %0.2f" %lam) 
print("The mean service rate per second: %0.2f"%mu) 
rho=lam/(c*mu) 
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c) 
for i in range(0,c): 
   sum=sum+(lam/mu)**i/math.factorial(i) 
P0=1/sum 
if(rho<1): 
   Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2 
   Ls=Lq+lam/mu 
   Ws=Ls/lam 
   Wq=Lq/lam 
   print("Average number of objects in the system: %0.2f"%Ls) 
   print("Average numner of objects in the conveyor: %0.2f"%Lq) 
   print("Average waiting time of an object in the system: %0.2f secs"%Ws) 
   print("Average waiting time of an object in the conveyor: %0.2f secs"%Ws) 
   print("Probability that the system is busy: %0.2f" %(rho)) 
   print("Probability that the system is empty:%0.2f "%(1-rho)) 
else: 
   print("Warning! Objects overflow will happen in the conveyor") 
print("-----------------------------------------------------")
```
## Output :
<img width="702" height="322" alt="image" src="https://github.com/user-attachments/assets/eab7a942-7395-4f0f-87c6-cbebd6c7529b" />

## Result : 

