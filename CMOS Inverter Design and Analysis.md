# CMOS Inverter Design and Analysis using Open Source tools
#
#
# Open Source Tools
 As I mentioned in Readme file , I provided all the Open Sources I used in this Project. You can refer this
#
## 1. SkyWater 130 PDK
# ![image](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/4ad9174a-0de7-4ccc-8593-8be58afe1afb)
#
The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit and related resources, which can be used to create manufacturable designs at SkyWater’s facility. The PDK can be downloaded on GitHub and converted to a so called Open-PDKs format with Open-PDKs. That format is the requirement to use it with the LayoutEditor.
#
#
## 2. Xschem 
# ![image](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/e85e2e83-85d9-434a-940e-963a933a18e9)
#
Xschem is a schematic capture program that allows to interactively enter an electronic circuit using a graphical and easy to use interface. When the schematic has been created a circuit netlist can be generated for simulation.
#
# 
## 3. Ngspice
# ![image](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/c62cecf5-a1e6-4b33-b2ff-3ab001f6f457)
#
Ngspice is the open source spice simulator for electric and electronic circuits. Ngspice is an open project, there is no closed group of developers.
#
#
## 4. Magic
# ![image](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/3c22dabd-6874-4369-a5c5-a540354e8dc8)
#
Magic is a VLSI layout tool.
#
#
#
#
# Design and Analysis of NMOS
#
## 1. NMOS design 
Firstly makesure to setup Sky130 pdk and Xschem on your system. Basically Xschem is a open source platform for design and simulating the design. 
#
Here I am using                                                                                                                                                                                                                                                                                                                                             
nfet_01v8.sym  - nmos transistor                                                                                                                                                                                
vsource.sym    - voltage source                                                                                                                                                                                                                                                                        
gnd.sym        - ground
#
This is the schematic which i created in xschem using above mentioned components
![Screenshot from 2023-12-08 16-33-35](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/400bb3e3-c0ea-417e-905e-402628d5837b)
#
## 2. DC sweep
DC sweep performs a sequence of DC operating point simulations. It increments the voltage or current of a selected source in predefined steps over a range of values. DC sweep can be used with any source that includes a DC offset variable. An optional second source can also be used to run a nested sweep.                                                                                   

In this DC sweep we are working two voltages **VGS** and **VDS** .VGS is the voltage present between Gate terminal and Source terminal .VDS is the voltage between Drain and Source terminals.Here we are analyzing DC current **Id** at drain terminal w.r.t variations on VDS and VGS.                                                                                                  
Here from Xschem library we have to add **codeshown.sym** to before design . This is used to perform simulation on design with one voltage keeping another voltage constant and we have to mention starting and ending voltages as well as rise value. The schematic shown below


![Screenshot from 2023-12-20 21-24-48](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/824a27fa-2cd9-44ab-8551-dd3a95796952)
#
#
graph for variation of Id for constant **Vds** and different **Vgs** values 
![Screenshot from 2023-12-08 16-41-10](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/5a827548-f595-47ca-b310-5b876c145783)
#
#
graph for variation of Id for constant **Vgs** and different **Vds** values
![Screenshot from 2023-12-08 16-35-57](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/a471f11b-c335-4e69-833e-8c32ca540e42)














