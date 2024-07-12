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

## Library binding & Placement

Library binding and placement are essential steps in the VLSI design flow, particularly during the physical design stage. These processes involve selecting the appropriate standard cell libraries and accurately placing them on the chip to meet design specifications such as performance, power, and area. Here’s a detailed explanation of each:

#### Library Binding in VLSI
What is Library Binding?

Library binding involves selecting and associating the appropriate standard cell libraries, which contain pre-designed and pre-verified logic gates, flip-flops, and other components, with the design. These libraries provide the building blocks for the digital circuit and are crucial for synthesizing and implementing the design.

Components of a Standard Cell Library:

Cells: Pre-designed logic gates, flip-flops, latches, and other basic building blocks.

Characterization Data: Timing, power, and area information for each cell under various operating conditions.

Layouts: Physical representations of each cell, including metal layers, vias, and diffusion regions.

Abstract Views: Simplified representations used for placement and routing.

Verification Models: Spice models and other data for simulation and verification.

#### Importance of Library Binding:
Performance: Ensures that the selected cells meet the timing requirements of the design.

Power: Helps in choosing low-power cells to meet power consumption targets.

Area: Aids in optimizing the area by selecting compact cells.

Manufacturability: Ensures that the cells are compatible with the fabrication process.

![Screenshot (641)](https://github.com/user-attachments/assets/d9c8ce74-10d5-4cff-a62c-4b20144a48e0)

## Placement in VLSI
What is Placement?
Placement involves positioning the standard cells on the chip after the design has been synthesized. The goal is to arrange the cells in a way that minimizes wirelength, meets timing constraints, and ensures routability.

#### What is Placement?
Placement involves positioning the standard cells on the chip after the design has been synthesized. The goal is to arrange the cells in a way that minimizes wirelength, meets timing constraints, and ensures routability.

#### Steps in Placement:

Initial Placement: Initial positions for all cells are determined based on connectivity and design constraints. Tools often use algorithms like min-cut, simulated annealing, or force-directed methods.

Global Placement: A rough placement is done to distribute the cells evenly across the chip, ensuring that the design is balanced and that no region is overly congested.

Detailed Placement: Fine-tuning of cell positions to resolve overlaps, further minimize wirelength, and meet timing requirements. This step involves iterative optimization.

#### Objectives of Placement:

Timing Closure: Ensures that the critical paths meet the timing requirements
.
Minimized Wirelength: Reduces the total wirelength, which helps in meeting timing constraints and reduces power consumption.

Congestion Management: Avoiding routing congestion by distributing cells evenly and leaving enough space for interconnects.

Thermal Considerations: Distributing power-hungry cells to manage heat dissipation.

#### Placement Algorithms:

Min-Cut Placement: Divides the design into smaller partitions to minimize the number of interconnections between them.

Force-Directed Placement: Models cells as objects influenced by forces, optimizing their positions to balance connectivity and separation.

Simulated Annealing: Uses a probabilistic technique to explore different placements and gradually improves the solution by minimizing a cost function.

Quadratic Placement: Uses quadratic cost functions to place cells based on their connectivity.

![Screenshot (644)](https://github.com/user-attachments/assets/802db9af-3ef2-4023-b6fb-b54d14adcf7e)

## LAB(DAY 2) For Placement:

### STEP 1:
use the command run_placement,after performing synthesis & floorplan.

![Screenshot (660)](https://github.com/user-attachments/assets/db3db240-9652-49b8-a41d-3696d1b03939)

### STEP 2:
move to the designated directory as shown in below image and invoke the magic for placement.

![Screenshot (665)](https://github.com/user-attachments/assets/1bb1f9f1-32d7-4592-ae75-32e84762e503)

![Screenshot (666)](https://github.com/user-attachments/assets/456e970d-3ec6-46a6-9993-d343cdcb93fa)

![Screenshot (724)](https://github.com/user-attachments/assets/02bc5def-2d6a-4d9a-af0b-bace2d474421)

## Cell design flow

library contains different types of standard cells,also cells with same name but different shapes are considered as different.

![Screenshot (669)](https://github.com/user-attachments/assets/84e5aa09-842b-43b7-897e-86288802b9cc)

the below image depicts the cell design flow

![Screenshot (671)](https://github.com/user-attachments/assets/3db9570a-93e4-4866-9829-f6e45ce28f2f)

the characterization flow has total of 8 steps and they ae processed by software GUNA,the result of this software is timing,noise,power information of the circuit

![Screenshot (701)](https://github.com/user-attachments/assets/7b1151b7-b23a-4881-b617-e55a6e81b2f0)
![Screenshot (700)](https://github.com/user-attachments/assets/26113516-59ac-4380-9e28-27e137a3906e)
![Screenshot (705)](https://github.com/user-attachments/assets/34fd5a20-10e3-45ee-b056-dd2c3dae0db3)

## Timing parameters & consideration

taking the case of buffer,input is applied on it.various analysis are taken into consideration for input and output slew rates,I/P & O/P rise and fall times.

![Screenshot (707)](https://github.com/user-attachments/assets/afbafa58-d301-4577-811f-bf62859abd7a)
![Screenshot (708)](https://github.com/user-attachments/assets/ec64a80d-fed1-4ac9-a188-49cf3b46a353)
![Screenshot (709)](https://github.com/user-attachments/assets/e6a6f973-bc51-4e5d-96b4-67901de9abe1)
![Screenshot (710)](https://github.com/user-attachments/assets/0a99c08e-9ec7-449b-b818-ccb4aea44e7a)
![Screenshot (711)](https://github.com/user-attachments/assets/7ba78161-6c2f-49ef-b191-973fb41149e6)
![Screenshot (712)](https://github.com/user-attachments/assets/ae61490b-dc0d-4318-9bea-86eee4e9a302)
![Screenshot (713)](https://github.com/user-attachments/assets/07e48a35-8db8-4c64-a299-377c8651e874)
![Screenshot (714)](https://github.com/user-attachments/assets/444a4097-e81d-4cd2-9a21-99dc4892a5e8)

+ve propagation delay:
![Screenshot (718)](https://github.com/user-attachments/assets/ac961865-acd4-4e18-916d-5a3acfc76cfa)

-ve propagation delay:
![Screenshot (719)](https://github.com/user-attachments/assets/ad93fb39-0825-47ba-8758-4d59774dfe2d)

I/P transition time:
![Screenshot (721)](https://github.com/user-attachments/assets/276bdccf-349e-42a7-93e1-03d0d2eaa46d)

O/P transition time:
![Screenshot (722)](https://github.com/user-attachments/assets/9cb8d065-c1d0-4666-b92f-73836a790068)

transition delay:
![Screenshot (723)](https://github.com/user-attachments/assets/a28705fb-9164-4482-a979-64fe075b6a67)

### This marks the end of DAY 2.
