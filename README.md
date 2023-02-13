# msvsd3bitfadc
10 week VSD research program


## Week 1: Inveter Pre-layout & Post-layout characterization:

#Simulation of CMOS Inverter using Xschem and Ngspice

launch `Xschem` in the chosen dir:
```
rupesh@rupesh:~/work/lab_inv/xschem$ xschem
```
following window opens

![image](https://user-images.githubusercontent.com/94752269/218549570-dd1b429b-3f39-423c-83a2-35c4408aa1e3.png)

1. Pre-layout characterization in Xschem and ngspice
  1. DC transfer function analysis
  ![inv_VTC 2](https://user-images.githubusercontent.com/94752269/218339465-58f6708d-e84e-4170-8f98-3cb4fc373bf3.png)
  
  ![inv VTC analysis](https://user-images.githubusercontent.com/94752269/218339467-4764799b-4ba5-4be3-8d0f-0e3872e1efa6.png)
  
  ![vin vs vout dc](https://user-images.githubusercontent.com/94752269/218339476-f5e02283-485b-4556-8917-b878bbda7b30.png)
  
  2. Transient Analysis
   ![inv_transient_analysis ](https://user-images.githubusercontent.com/94752269/218339460-65ea48d1-3a83-438f-a2a8-8d44b352cc4b.png)
   
   ![inv_transient_analysis_wave](https://user-images.githubusercontent.com/94752269/218339462-cf4d5cae-20a6-4453-b304-4bc9d3fcf9b0.png)
   
2. Post-layout characterization in Magic
![myinv_magic](https://user-images.githubusercontent.com/94752269/218339474-2f9cea90-48af-4fd3-ad22-77a8d5d7dff6.png)

![my_inv2](https://user-images.githubusercontent.com/94752269/218339471-0ecc5ee0-b322-4ad5-87d6-2690e1a558d6.png)

  1. DC transfer function analysis
  
![post_layout dc](https://user-images.githubusercontent.com/94752269/218552649-b6b889de-7450-4bcd-bb45-4261f720a4ba.png)

 
  2. Transient Analysis

![post layout transient](https://user-images.githubusercontent.com/94752269/218552771-f0a1fadf-2226-434c-9ea3-aa4b850f2599.png)


