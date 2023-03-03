# Week 2: OpenFASoc and OpenROAD

Contents

Sr. No | Topic | Description | Status |
---|---|---|---|
1 | OpenFASoc: Installation| installing OpenFASoc| :heavy_check_mark:|
2 | OpenROAD: Installation  | installing OpenROAD  |  :heavy_check_mark: |  |
3 | Temperature Sensor: AUX Cells | View & study temperature sensor design using OpenFASoc & OpenROAD |  :heavy_check_mark:  |

## OpenFASoc: Installation
----

```
cd ~/work
git clone https://github.com/idea-fasoc/openfasoc
cd openfasoc
sudo ./dependencies.sh
```
## OpenROAD: Installation

OpenROAD is an integrated chip physical design tool that takes a design from synthesized Verilog to routed layout.

An outline of steps used to build a chip using OpenROAD is shown below:

    1. Initialize floorplan - define the chip size and cell rows
    2. Place pins (for designs without pads )
    3. Place macro cells (RAMs, embedded macros)
    4. Insert substrate tap cells
    5. Insert power distribution network
    6. Macro Placement of macro cells
    7. Global placement of standard cells
    8. Repair max slew, max capacitance, and max fanout violations and long wires
    9. Clock tree synthesis
    10. Optimize setup/hold timing
    11. Insert fill cells
    12. Global routing (route guides for detailed routing)
    13. Antenna repair
    14. Detailed routing
    15. Parasitic extraction
    16. Static timing analysis


```
cd ~/work
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD.git
cd OpenROAD
sudo ./etc/DependencyInstaller.sh
sudo ./etc/DependencyInstaller.sh -run
sudo ./etc/DependencyInstaller.sh -dev

cd ~/work
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts
cd OpenROAD-flow-scripts
./build_openroad.sh –local
export OPENROAD=~/work/OpenROAD-flow-scripts/tools/OpenROAD
export PATH=~/work/OpenROAD-flow-scripts/tools/install/OpenROAD/bin:~/work/OpenROAD-flow-scripts/tools/install/yosys/bin:~/work/OpenROAD-flow-scripts/tools/install/LSOracle/bin:$PATH
```
## Install Yosys

Note: refer official [Yosys](https://github.com/The-OpenROAD-Project/yosys) github page for detailed installation guide.

install dependencies using following commands (for Ubuntu)

```
$ sudo apt-get install build-essential clang bison flex \
	libreadline-dev gawk tcl-dev libffi-dev git \
	graphviz xdot pkg-config python3 libboost-system-dev \
	libboost-python-dev libboost-filesystem-dev zlib1g-dev
```
installation:

```
git clone https://github.com/YosysHQ/yosys.git
cd yosys
make config-gcc

make
sudo make install

//test installation using 
make test
```

## Temprature Sensor Generation OpenFASoC flow:

In this section we will test and try OpenFASoC flow with the help of temeprature sensor design comes with the openFASoC

## GDS files:

Header GDS

![Header GDS](/week2/images/Header%20GDS.png)

SLC GDS

![SLC GDS](/week2/images/SLC%20GDS.png)

## verilog generation:

![Verilog gen](/week2/images/temp-sense-gen-verilog.png)

![Verilog gen](/week2/images/temp-sense-gen-verilog2.png)

## synthesis

## floorplan

![floorplan](/week2/images/temp-sense-gen-floorplan.png)


## Placement

Global placement
![Global placement](/week2/images/temp-sense-gen-global-place-report.png)

detailed placement
![detailed placement](/week2/images/temp-sense-gen-detailed-placement-report.png)

## Routing

Global Routing
![Global Routing](/week2/images/temp-sense-gen-global-route-report.png)

## Final GDS layout

finished-report
![finished-report](/week2/images/temp-sense-gen-finished-report.png)

Final GDS Layout
![Final GDS Layout](/week2/images/temp-sense-gen-final-gds-layout.png)

## Post-layout verification

DRC Check
![DRC](/week2/images/temp-sense-gen-DRC.png)

Layout Vs Schematic Check
![LVS](/week2/images/temp-sense-gen-LVS.png)