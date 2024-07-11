# Physical_design:-
Physical design refers to the phase in the process of creating computer chips where the detailed physical layout of the circuitry is determined. In simpler terms, it's like designing the blueprint or map of how all the tiny electronic components (like transistors and wires) will be arranged on a computer chip.

# NASSCOM-VSD-PD-WORKSHOP
it consisted of 5 day workshop conducted by VSD and NASSCOM on RTL 2 GDS flow.
a brief introduction was given about frontend and main focus was on backend flow.
VSD-IAT cloud platform was used to provide acess to lectures.

## WORKSHOP FLOW:-
1.Introduction to open source eda tool(openlane) and PDK(skywater130nm).

2.Floorplanning and Powerplanning.

3.cell design using Magic Layout and Ngspice characterization.

4.Pre-layout timing analysis and importance to good clock tress(i.e minimum skewness).

5.Final steps for RTL2GDS flow.


## Authors

- [Gaurang kumar Sharma](https://www.linkedin.com/in/gaurang-sharma-983a6820a/?originalSubdomain=in)

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




