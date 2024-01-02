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
                                                                                                                                                                                                         
And here we are analysing the two parameters gm and gds (transconductances) which are crucial in findng other characterstics

gm is derivative of id current with constant **Vds** and different **Vgs** values i.e d(Id)/dVgs
![Screenshot from 2023-12-10 19-32-14](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/575c4093-15d1-4731-9c78-e9b4d2c90f6f)

gds or ro is derivative of id with constant **Vgs** and different **Vds** values i.e d(Id)/dVds
![Screenshot from 2023-12-10 20-11-49](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/c5c9a57e-9728-4bd5-8aee-b555fad4b7b4)
                                                                                                                                                                                                                                                                                                                                                                                                                  
#
#

# Design and Analysis on PMOS
#

## 1. PMOS Design
similarly I am designing the PMOS with given components
                                                                                                                                                                                                   
pfet_01v8.sym - pmos Transistor                                                                                                                                                                                                                                                                                                                                         
vsource.sym   - voltage source                                                                                                                                                                       
gnd.sym       - ground                                                                                                                                                                            

This is the schematic which i created in xschem 
![Screenshot from 2023-12-09 19-59-35](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/3a4c3e80-28e9-470e-ba0e-f81ebf52e69a)                                                                                             
 Here i also added codeshown.sym and provided the code for dc sweep simulation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
## 2. DC sweep
So after simulating the design of pmos with                                                                                                                                                             
graph for variation of Id for constant **Vds** and different **Vgs** values                                                                                                                        
graph for variation of Id for constant **vgs** and different **Vgs** values                                                                                                                               
gm is derivative of id current with constant **Vds** and different **Vgs** values i.e d(Id)/dVgs                                                                                                      
gds or ro is derivative of id with constant **Vgs** and different **Vds** values i.e d(Id)/dVds                                                                                                         
#
#
#

# CMOS Inverter Design and Analysis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
## 1. CMOS Inverter Design                                                                                                                                                                               
CMOS stands for complementary Metal Oxide Semiconductur which means it consists of two complementary Mosfets i.e NMOS and PMOS . In Inverter design we have to keep Drain terminal of Nmos and Pmos get connected. The design should be like below                                                                                                                                                 
![Screenshot from 2023-09-28 17-54-12](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/bfab72aa-d732-420b-b3f5-68a6625bff81)
                                                   
#
#
## 2. VTC Analysis on CMOS                                                                                                                                                                           
VTC stands for Voltage Transfer Characterstics means how the input voltage transfer to output voltage . Here we are using a constant Vdd voltage 1.8v .                                                 
Before that I am creating a symbol for this CMOS inverter by clicking "A" on my system .Then it will create a symbol and I can get it on my library  and use it for Schematic. Schematic od design before simulation.                                                                                                                                                                                  
![Screenshot from 2023-09-28 17-53-57](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/8cc7e4d6-2975-4c45-9dbc-60582e5e7612)                                                                                                                                                                                                                           
Characterstic curve after simulation could be like shown below                                                                                                                                                                                                                                                                                                                                                                
#
![Screenshot from 2023-12-12 16-26-38](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/32b057af-c525-4e30-adad-edb98fa07461)
#
Here we can find Threshold voltage Vth i.e voltage vin where vout and vin curve got intersected

#
## 3. NOISE Analysis on CMOS                                                                                                                                                                                 
In Noise Analysis we are finding the region where the output is indeterministic to the input provides. For that firstly we need to findout the gain which the derivative of Vout of CMOS inverter.                                                                                                                                                                                                                                
  #                                                                                                                                                                                                                                       
![Screenshot from 2023-12-13 13-22-21](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/57ef63db-edfd-4e9d-86be-2135b513b9df)
                                                                                                                                                                                                                 
then  plot  the absoulte value of gain 
![Screenshot from 2023-12-13 13-29-27](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/9f779639-e1a3-4872-9139-09d1155ac721)                                                                                                                                                                                                                                                                                                     
then plot gain and vout in same graph to finout **VIL** and **VIH**                                                                                                                                         
**VIL** is the highest input which is considered as  lowest logic input                                                                                                                            
**VIH** is the lowest input which is considered as highest logic input                                                                                                                                                                                                                              
#
![Screenshot from 2023-12-13 13-50-52](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/b7edcf07-ed78-4bca-9a75-c542ee66d40f)          
              ![Screenshot from 2023-12-13 13-51-44](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/989e3348-c12b-4054-9b86-66afd4e14f9e)                                                                                                                                                                                                                                                                                                                                                                                              
  From the values we obtained we can conclude the input values between **VIH** and **VIL** provides the invalid output. so the region between **VIL** and **VIH** is defined as Noise region                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
#
#
## 4. Delay Analysis on CMOS
#

![image](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/79978df7-62b6-475a-8e08-fb76808239df)
firstly let us see definitions of some of the important parameters of delay in Cmos inverter
                                                                                                                                                                                                            
**1.Propagation delay High to Low (tpHL)** : delay when output switches from high-to-low, after input switches from low-to-high. 
**2.Propagation delay Low to High (tpLH)** : delay when output switches from low-to-high, after input switches from high-to-low. 
**3.Rise time (tR)** : Rise time (tr) is the time, during transition, when output switches from 10% to 90% of the maximum value.
**4.Fall time (tF)** : Fall time (tf) is the time, during transition, when output switches from 90% to 10% of the maximum value.
#
#
Let us simulate the following schematic and find out the above parameters
![Screenshot from 2023-12-22 10-19-52](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/7b56f858-cc7d-4d80-8289-5523f3ef149c)
![Screenshot from 2023-12-22 10-28-25](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/fe120c4b-29f7-402a-ba96-201704b0a17d)


Here we are using transient analysis for finding required once 
![Screenshot from 2023-12-22 20-55-18](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/f859aadd-2067-436f-9fd9-694c664c71ec)
![Screenshot from 2023-12-23 11-51-07](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/6a0dfe82-99ce-4495-b316-4a177a1d45d6)



factors of Rise time and Fall time
**1.vdd supply** : delay decreases when vdd supply increases (inversly proportional)
**2.silicon area** : delay decreas when silicon area increases (inversly proportional)
**3.load capacitance** : delay increases when load capacitance increases (direcly proportional)

#
when vdd supply increases from 1.8 to 2v

![Screenshot from 2023-12-23 11-46-42](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/0a5fddee-461a-43a1-a934-88102ab3fcc8)

#
when silicon area i.e W value of pfet and nfet increases 

![Screenshot from 2023-12-23 12-22-43](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/b128bb5a-3277-41da-8ae4-a33769f4cb33)

# 
when keeping load capacitance of 1pf at output port

![Screenshot from 2024-01-02 11-09-00](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/84909ca3-f069-4fa9-ab10-a90f6ef2ef7b)
![Screenshot from 2023-12-24 10-35-11](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/2a24b75a-b0a6-4312-b6fd-f22f01cc81e9)
![Screenshot from 2023-12-24 10-36-41](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/39662e49-2b78-40f2-9972-952092fbe81a)

futher vdd  supply decreases then delay further more increases

![Screenshot from 2023-12-24 10-47-21](https://github.com/Harinath7259/CMOS-Inverter-Design-and-Analysis-using-Open-Source-tools/assets/146565066/24fe0e65-6ceb-49fa-8ecd-1279769bb2a8)





















