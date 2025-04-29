<div style="text-align: center;"> <img src="https://rivanit.com/assets/logo-DaYZ0U1G.png" alt="Logo" title="TH_Lab Logo" /> <h1>DAY 1 TH_Lab</h1> <h2>Task 1: Physical Ports Check</h2> <h3>Power over Ethernet (PoE) Status</h3> </div>

```cisco
CallCenter-28#show power inline 
PowerSupply   SlotNum.   Maximum   Allocated       Status
-----------   --------   -------   ---------       ------
INT-PS           0        88.000    28.800          PS GOOD
Interface   Config   Device   Powered    PowerAllocated
---------   ------   ------   -------    -------------- 
Fa0/1/0     auto     Unknown  Off        0.000 Watts  
Fa0/1/1     auto     IEEE-2   On         7.000 Watts  
Fa0/1/2     auto     Unknown  Off        0.000 Watts  
Fa0/1/3     auto     IEEE-2   On         6.400 Watts  
Fa0/1/4     auto     Unknown  Off        0.000 Watts  
Fa0/1/5     auto     IEEE-4   On        15.400 Watts  
Fa0/1/6     auto     Unknown  Off        0.000 Watts  
Fa0/1/7     auto     Unknown  Off        0.000 Watts 
```
