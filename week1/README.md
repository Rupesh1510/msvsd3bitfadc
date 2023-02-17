# Week 1: Inveter Pre-layout & Post-layout characterization:

Contents

Sr. No | Topic | Description | Status |
---|---|---|---|
1 | Inverter| Pre-layout| :heavy_check_mark:|
  |   |   |   |  |
  |   |   |   |  |
  |   |   |   |  |
  |   |   |   |  |
  |   |   |   |  |

## Simulation of CMOS Inverter using Xschem and Ngspice

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


## Generating GDS file using ALIGN

input- netlist exported from xschem
output- INVERTER_0.gds
        INVERTER_0.python.gds

install KLayout

```
sudo apt-get install qttools5-dev libqt5xmlpatterns5-dev qtmultimedia5-dev libqt5multimediawidgets5 libqt5svg5-dev
git clone https://github.com/KLayout/klayout
cd klayout/
./build.sh -prefix /usr/bin
```

![terminal screenshot](week1/pictures/gds inverter.png "ALIGN")

```
* SPICE3 file created from INVERTER.ext - technology: sky130A
.lib /usr/local/share/pdk/sky130A/libs.tech/ngspice/sky130.lib.spice tt
.option scale=5000u

inv1 A Y Vpwr Vgnd inverter

.subckt inverter A Y Vpwr Vgnd
X0 A Y Vgnd Vgnd sky130_fd_pr__nfet_01v8 ad=117600 pd=4760 as=138600 ps=5700 w=420 l=30
X1 A Y Vgnd Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X2 Vgnd Y A Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X3 Vgnd Y A Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X4 A Y Vgnd Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X5 Vpwr Y A Vpwr sky130_fd_pr__pfet_01v8 ad=138600 pd=5700 as=117600 ps=4760 w=420 l=30
X6 A Y Vpwr Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X7 A Y Vpwr Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X8 Vpwr Y A Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X9 A Y Vgnd Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X10 A Y Vpwr Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X11 Vpwr Y A Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X12 Vgnd Y A Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X13 Vpwr Y A Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X14 A Y Vpwr Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X15 A Y Vpwr Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X16 Vpwr Y A Vpwr sky130_fd_pr__pfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X17 A Y Vgnd Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X18 Vgnd Y A Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
X19 Vgnd Y A Vgnd sky130_fd_pr__nfet_01v8 ad=0 pd=0 as=0 ps=0 w=420 l=30
C0 Vpwr Y 2.60fF
C1 Vpwr A 4.03fF
C2 A Y 1.21fF
C3 A Vgnd 3.26fF **FLOATING
C4 Y Vgnd 2.98fF **FLOATING
C5 Vpwr Vgnd 5.22fF **FLOATING
.ends

*set Vpwr and Vgnd
Vss Vgnd 0 0
Vdd Vpwr Vgnd 1.8

*create pulse 
Vin A Vgnd pulse(0 1.8 1ns 1ns 1ns 4ns 10ns)

.tran 0.01n 60n
.save all
.end
```