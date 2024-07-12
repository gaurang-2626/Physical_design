# Physical_design:-
Physical design refers to the phase in the process of creating computer chips where the detailed physical layout of the circuitry is determined. In simpler terms, it's like designing the blueprint or map of how all the tiny electronic components (like transistors and wires) will be arranged on a computer chip.

# NASSCOM-VSD-PD-WORKSHOP
it consisted of 5 day workshop conducted by VSD and NASSCOM on RTL 2 GDS flow.
a brief introduction was given about frontend and main focus was on backend flow.
VSD-IAT cloud platform was used to provide acess to lectures.

## WORKSHOP FLOW:-
1.Introduction to open source eda tool(openlane) and PDK(skywater130nm).

2.Floorplan and Powerplan.

3.cell design using Magic Layout and Ngspice characterization.

4.Pre-layout timing analysis and importance to good clock tress(i.e minimum skewness).

5.Final steps for RTL2GDS flow.


## Authors

- [Gaurang kumar Sharma](https://www.linkedin.com/in/gaurang-sharma-983a6820a/?originalSubdomain=in)

# DAY 1:-

## 1. Interaction with computers
![Screenshot (544)](https://github.com/gaurang-2626/Physical_design/assets/175235170/8999a1b1-e67d-4093-aa1e-8a8f91542592)

This is arduino uno board,the encircled part is the processor which we are concerned about.
we will be doing physical design of macro present inside the processor.(i.e)we will be implementing block level design.

the image shown below shows the microcontroller board or PCB on which different components are placed.

![Screenshot (545)](https://github.com/gaurang-2626/Physical_design/assets/175235170/d7773efb-b393-474f-925e-a7c01757e6ca)

This image contains various interconnecting devices such as EPROM,SDRAM,ADC & DACs,peripherals of microcontroller etcs.

. The centre part is the processor,highlighted on the arduino board.

. remaining part are the other components on board.




####
Now we will dive deep into the discussion and look forward towards processor,

the image below depicts the processor.

it has chip in the centre and connected to pins with the help of bond wires and interconnect wires.

![Screenshot (546)](https://github.com/gaurang-2626/Physical_design/assets/175235170/4b7f0158-9645-4061-9f23-1ac9684c1ef8)

The core consist of mainly two parts:-

1)IPs:
 In the context of VLSI (Very Large Scale Integration), "IPs" stands for "Intellectual Property." In this domain, IPs refer to pre-designed functional blocks or modules that can be integrated into a larger chip design. These IPs are typically designed to perform specific functions, such as arithmetic operations, communication protocols, memory interfaces, or even entire processor cores.

2)Macros:-macros" refer to pre-designed and pre-verified circuit blocks that are typically larger in size and complexity compared to IPs (Intellectual Properties). Macros are often complete functional units or subsystems that can be integrated into a chip design. Here are some key points about macros in VLSI:
![Screenshot (547)](https://github.com/gaurang-2626/Physical_design/assets/175235170/cfa97239-3d74-4b1d-9f9d-1a3934e1323b)

The below given image depicts the RISCV architecture to implement a SOC.it show RTL2GDS flow.

![day16](https://github.com/gaurang-2626/Physical_design/assets/175235170/98b81312-a479-443a-a6b8-92f9a7e066e1)

Moving forward we look into how the application software or apps interact with the hardware.

we are actually unaware of what goes in backend,so this image shows the exact flow of information from app to hardware.

![Screenshot (440)](https://github.com/gaurang-2626/Physical_design/assets/175235170/992c1fe2-b134-4ae0-88e9-06e98f24452b)

taking an example of stopwatch this can be explained in an easy way.

![Screenshot (444)](https://github.com/gaurang-2626/Physical_design/assets/175235170/946d4394-7f9e-4388-b918-621d3e8a8ac2)

conversion of binary code into HDL is done which gives information about functionality of the the program.

in next step RTL is syntesized and we perform Physical design of obtained netlist.

![Screenshot (449)](https://github.com/gaurang-2626/Physical_design/assets/175235170/d5c5d452-101b-4af8-89e6-e3d480ea15ad)

## SOC Design and Openlane

the flow diagram of RTL2GDS is shown below with complete information.

![Screenshot (466)](https://github.com/gaurang-2626/Physical_design/assets/175235170/d19df1b5-aad5-4ae5-b5f2-854126ae8d8a)


Synthesis is the process of converting a high-level hardware description into a lower-level representation that can be implemented on a silicon chip. This involves transforming the abstract design, written in a hardware description language (HDL), into a gate-level netlist, which is a description of the circuit in terms of logic gates and their connections.

![Screenshot (467)](https://github.com/gaurang-2626/Physical_design/assets/175235170/894071cc-57a7-4b1c-848a-ed3bcb9e6e86)

Floorplanning is the process of defining the size, shape, and placement of various blocks and modules within a chip. It is an essential step that sets the foundation for the placement and routing of a VLSI design.

Power planning is the process of designing the power distribution network within a chip to ensure that all parts of the circuit receive stable and adequate power.

![Screenshot (469)](https://github.com/gaurang-2626/Physical_design/assets/175235170/61bfc5f1-26fb-40d5-87a7-292acac0f941)

![Screenshot (471)](https://github.com/gaurang-2626/Physical_design/assets/175235170/c8bd9b10-870e-4f1a-8967-6b0edc80264c)

Placement is the process of determining the exact locations of standard cells, macros, and other circuit components within the chip area defined during floorplanning. This step is crucial for optimizing the chip's performance, power consumption, and manufacturability.

it is of 2 types:Global and Detailed Placement

![Screenshot (472)](https://github.com/gaurang-2626/Physical_design/assets/175235170/d4f71eb2-84a0-43c0-9f0e-0d0e70fb9f3d)

![Screenshot (474)](https://github.com/gaurang-2626/Physical_design/assets/175235170/537cb2a8-6cbc-40dc-bc9f-68e77c21aaef)


Clock Tree Synthesis (CTS) is a critical step in the physical design phase . CTS is responsible for designing and optimizing the clock distribution network to ensure that the clock signal reaches all sequential elements (flip-flops and latches) with minimal skew and optimal timing.

![Screenshot (475)](https://github.com/gaurang-2626/Physical_design/assets/175235170/7c94939c-3530-4cd8-9655-718f927c16e5)

Routing is a key step in the physical design phase. After placement and Clock Tree Synthesis (CTS), routing involves creating the physical connections between the various components (standard cells, macros, I/O pins, etc.) on the chip. This step ensures that the electrical signals can travel between the components as needed.

![Screenshot (476)](https://github.com/gaurang-2626/Physical_design/assets/175235170/278d1e5f-de83-4b7e-8b11-a7fc5712a746)

the last stage is the signoff checks that includes LVS & DRC.

![Screenshot (478)](https://github.com/gaurang-2626/Physical_design/assets/175235170/c6f83f37-4b18-42dd-ac7f-05874b3183f6)


## Lab(DAY1) using Open source EDA tools:

### STEP 1:
Now we will begin our journey to implement PD using open source EDA tool,so far we have completed the ovierview and necessary theory regarding RTL2GDS flow.

Go to the directory(work) where you will need to invoke the tool openlane.

![Screenshot (530)](https://github.com/gaurang-2626/Physical_design/assets/175235170/9614b0a2-c45c-4dd8-bba6-049449aae27a)

![Screenshot (531)](https://github.com/gaurang-2626/Physical_design/assets/175235170/54bb826f-0ef9-481a-9d23-85759ee5762b)

### STEP 2:
after invoking the openlane tool,we need to work in interactive mode & under design list we have to use picorv32a

![Screenshot (533)](https://github.com/gaurang-2626/Physical_design/assets/175235170/2d596022-6101-4ed8-8ddd-01f37a23ca70)

### STEP 3:
Now we need to perform synthesis using run_synthesis command.

![Screenshot (536)](https://github.com/gaurang-2626/Physical_design/assets/175235170/6f50701d-06c5-4997-b90d-272713f3317f)

### STEP 4:
Next crucial step is to calculate the flop ratio.

formaula:(number of D-ff/Total number of cells)

to get the result in % multiply by 100

given statistics:

![Screenshot (540)](https://github.com/gaurang-2626/Physical_design/assets/175235170/a8e9d847-38b4-4105-a241-67d9fae5fbd2)

![Screenshot (549)](https://github.com/gaurang-2626/Physical_design/assets/175235170/8520bd24-1956-4b86-b18a-9185240a78bb)

Number of D-ff=1613 & Total number of cells=14876

therefore,Flop ratio=(1613/14876)=0.1084296853993

Flop ration in  %=10.84296853993%

### This marks the end of DAY 1

# DAY 2
## Floorplan & Powerplan
in this module we will study about Floorplan & Powerplan,we begin with creating the netlist,definding width & height of core and die area.
below image shows the netlisting of ffs and gates.
![Screenshot (550)](https://github.com/user-attachments/assets/56379166-69d7-4284-81dd-af8b226b99f2)

now convert the netlist into physical dimensions.
gates are also converted as shown by boxes below.
![Screenshot (551)](https://github.com/user-attachments/assets/fcdae878-a1ba-4852-8651-44728f5bc795)

the measurement of cells anf ffs for calculation of core is necessary as depicted below.
Die consist of core,it is the part on which chip is fabricated.
![Screenshot (553)](https://github.com/user-attachments/assets/b3e59687-1608-4b27-b1f2-c91ec5e2285b)

two important parameters with respect to core & die are:

a)utilization factor

b)aspect ratio
![Screenshot (560)](https://github.com/user-attachments/assets/5884ee6a-8208-4f38-8576-6ed7d8ee4df3)

#### Importance of Floorplanning
Performance: Proper floorplanning can minimize the signal propagation delay and improve the overall performance of the chip.

Power Consumption: A well-planned floorplan can reduce power consumption by minimizing the length of interconnects.

Area Utilization: Efficient floorplanning ensures optimal usage of the available silicon area, reducing the chip size and cost.

Thermal Management: Distributing the heat-generating components evenly can prevent hotspots and improve the thermal performance of the chip.

####  Importance of Powerplanning
Voltage Stability:
Ensures stable supply voltage across the entire chip.
Prevents voltage drops that could cause circuit malfunction.

Performance Optimization:
Reduces IR drops, ensuring circuits operate at their intended speeds.
Minimizes timing variations caused by power supply fluctuations.

Power Integrity:
Maintains power supply noise within acceptable limits.
Prevents noise-induced signal integrity issues and functional errors.

![Screenshot (598)](https://github.com/user-attachments/assets/4a24a2f6-6748-4d7b-9428-dee868798e26)

the final pin placement on core of die can be depicted as below:

![Screenshot (606)](https://github.com/user-attachments/assets/5f0834cf-f880-40ea-a624-7e8ea60ee4c0)

the cell placement blockage is used to block the area between core and die such that no other std.cells or any other placement takes place in that area.this area is reserved only for IO pins.
![Screenshot (607)](https://github.com/user-attachments/assets/6fe8631c-d5a9-4a29-a09e-f2aa1cd2865a)

## LAB(DAY2) Floorplan:

### STEP 1:
use the command run_floorplan to execute the floorplan,it will take 4 to 5 minutes to execute this commmand

![Screenshot (616)](https://github.com/user-attachments/assets/dfa09d33-fd3f-4513-b343-e06453cd45a7)

### STEP 2:
the floorplan def file would be created,which can be read using less command

![Screenshot (618)](https://github.com/user-attachments/assets/eec85024-1b89-41c6-8af1-74513e093cd7)

### STEP 3:
Now to visually verify the created floorplan we use magic tool(to view layout),following command is used as shown in below image,this would lead to pop up of magic window where we can realise our floorpan.

![Screenshot (627)](https://github.com/user-attachments/assets/dfb652c5-588e-4598-adfb-7e056524ca94)
![Screenshot (631)](https://github.com/user-attachments/assets/fe83a730-a1db-419d-b323-0ca80f6da6ba)
![Screenshot (632)](https://github.com/user-attachments/assets/d816f7ef-1e52-4753-bdf3-6fdafcf14d6a)
![Screenshot (633)](https://github.com/user-attachments/assets/982696bf-6485-48fd-9c68-caba23d89a0c)












