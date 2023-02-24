# Week 2: OpenFASoc and OpenROAD

Contents

Sr. No | Topic | Description | Status |
---|---|---|---|
1 | OpenFASoc: Installation| installing OpenFASoc| :heavy_check_mark:|
2 | OpenROAD: Installation  | installing OpenROAD  |  :construction: |  |
3 | Temperature Sensor: AUX Cells | View & study temperature sensor design using OpenFASoc & OpenROAD |  :construction:  |

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
cd ~/work
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts
cd OpenROAD-flow-scripts
./build_openroad.sh –local
export OPENROAD=~/OpenROAD-flow-scripts/tools/OpenROAD
export PATH=~/OpenROAD-flow-scripts/tools/install/OpenROAD/bin:~/OpenROAD-flow-scripts/tools/install/yosys/bin:~/OpenROAD-flow-scripts/tools/install/LSOracle/bin:$PATH
```
