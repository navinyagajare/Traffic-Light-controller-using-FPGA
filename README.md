# Traffic-Light-controller-using-FPGA
A Verilog source code for a traffic light controller on FPGA is presented. A sensor on the farm is to detect if there are any vehicles and change the traffic light to allow the vehicles to cross the highway. 
# Traffic Light Controller Using Verilog
* The purpose of this project is to design a methodology using Verilog to control the traffic with specified time delays for a T-Shaped road.*

# Table of Contents

1. [Introduction](#Introduction)
2. [Methodology](#Methodology)
3. [RTL Code](#rtl-code)
4. [TESTBENCH](#testbench)
5. [Output Waveforms](#output-waveforms)
6. [Result](#result)
7. [Future work](#future-work)
8. [References](#references)
9. [Author](#author)


## Introduction 

Traffic control is a challenging problem in many cities. This is due to the large number of vehicles and the high dynamics of the traffic system. Poor traffic systems are the big reason for accidents, time losses. In this method of approach, it will reduce the waiting time of the vehicles at traffic signals. The hardware design has been developed using Verilog Hardware Description Language (HDL) programming. 

Verilog designing is hardware descriptive language, the name itself suggest that it deals with the hardware designing and simulation. Basically, it becomes very difficult to mount the various electronic components on breadboard or PCB circuit. It also takes too much time for the simulation and sometimes many errors occur because of improper connection of components onto the circuit. 
And thus, to overcome this factor hardware descriptive language comes into conclusion. we can code the process using Verilog and we can mount it on a circuit or just upload it to the circuit accordingly so that particular circuit will work as according to the code we have written. 

HDL language is often used for sequential circuits like shift register, combinational logic circuit like adder, subtractor etc. Basically it describes the digital systems like microprocessor or a memory. Whatever design that is described in HDL are independent, it has its unique state of work, very much easy to simulate, designing and debugging, and very useful than schematics, especially for large circuits thus, to overcome difficulties or problems to design the circuits manually with breadboard and PCB, use of Verilog designing in this complex world is increasing a way better. 

This project deals with a basic design of a T - Shaped road for traffic light control. The output of system has been tested using Xilinx 14.5. 

A traffic light system is an electronic device that assigns right of way at an intersection or crossing or street crossing by means of displaying the standard red, yellow and green colored indications. In addition, it also works in conjunction with pedestrian displays to assign pedestrian crossing right of way. 

A traffic light, also known as traffic signal, stop light, stop-and-go lights, is a signaling device positioned at a road intersection, pedestrian crossing, or other location in order to indicate when it is safe to drive, ride, or walk using a universal colour code.
Nowadays, 

1. A red light meant traffic in all directions had to stop. 
2. A yellow light meant cross-town traffic would have to slow and,
3. A green light would to go or proceed.

The problem of heavy jam is happened because of never configure the level of jam in each way and set the delay time. Another problem represents when there is no jam, but the waiting still continues. The solution for these problems is to determine the level of jam and set the delay time. This problem need of evaluation of the traffic policeman, and then there is need for manual control of the traffic. 
The target of this paper is to propose system provide solution for all above problems with least possible cost. Traffic light controller (TLC) can be implemented using microcontroller, FPGA, and ASIC design. FPGA has many advantages over microcontroller, some of these advantages are; the speed, number of input/output ports and performance which are all very important in TLC design, at the same time ASIC design is more expensive than FPGA. 
Nowadays, FPGA becomes one of the most successful of today’s technologies for developing the systems which require a real time operation. FPGA is a re-configurable integrated circuit that consists of two dimensional arrays of logic blocks and flip-flops with an electrically programmable interconnection between logic blocks. 
The reconfiguration property enables fast prototyping and updates for hardware devices even after market launch. Most of the TLCs implemented on FPGA are simple ones that have been implemented as examples of Finite State Machine (FSM).

#### The Verilog language has been selected for programming the FPGA to fill two important needs in the design process. 

- Firstly, it gives full description of the structure of a design that is how it is decomposed into sub-designs, and how those sub-designs are interconnected. 
- Secondly, it allows simulating the design before starting the manufacturing. 
- Accordingly, the designers can quickly compare alternatives and test for correctness without the delay and expense of hardware prototyping. 

#### Benefits of Using Verilog HDL (Hardware Description Language) : 

Verilog is a widely used Hardware Description Language (HDL) for designing digital circuits. It can also be used for modeling analog circuits. Verilog is a descriptive language that describes a relationship between signals in a circuit. 

A Verilog model describes a unit of digital hardware in terms of :
- Interconnections of other hardware unit whose models prescribe their behavior in a 
    simulation.
- Behavioral / procedural algorithms that abstractly describe input/output behavior    
       that could be personified in a hardware unit. 

Hardware description language (HDL) is divided by two types, Verilog and VHDL (VHSIC – Very High Speed Integrated Circuit Hardware Description Language). Both have its advantages and its disadvantage. 
In this project, Verilog HDL was chosen because it’s used for synthesis of logic circuits (synthesizable code), used for verification purposes of a circuit (can be analog or digital or mixed signal), can be used by combining synthesis & verification (synthesizable & behavioral code) and it used for netlist representation of a synthesizable circuit (structural code). 

#### The advantages using Verilog are shown below : 
- Easy to write. 
- Easy to understand as it similar to C program. 
- Easier to learn compared with VHDL.


## Methodology

 The code starts with a declaration of the variables that will be used in the program.
 The first variable is light_highway, which is an input to the traffic_light function.
 This means that this variable can only be set by code inside of the traffic_light function.
 The next two variables are clk and rst_n, which are inputs to the traffic light function as well.
 These two inputs have been declared as being active low so they must be connected together with a wire or else they would not work properly.
 The next line declares HGRE_FRED = 2'b00, HYEL_FRED = 2'b01, HRED_FGRE=2'b10, and HRED_FYEL=2'b11 for four different colors: green (HGRE), yellow (HYEL), red (HRED) and blue (HRDY).
 These values represent how much power each color should use on its corresponding sensor pin when it turns on.
 The code is used to control a traffic light.
 The first two lines of the code define the traffic light's inputs, which are the sensor and clock.
 The next line defines a parameter for each input, which are Highway Green and Farm Red.
 The next line defines a parameter for each input, which are Highway Yellow and Farm Red.
 Finally, there is an input for the Traffic Light itself, which can be either on or off (highway green or farm red).
 The purpose of this code is that if you set C=1 then it will turn on the traffic light; otherwise it will turn off.
 The code is a state machine that is triggered by the clock enable signal.
 The next state is determined by the current state and the value of count.
 The code begins with an always block, which will be executed every time clk or rst_n goes high (or low).
 In this case, it's always true because both signals are high (or low) so there's no need to specify when they go high or low.
 If you wanted to make sure that only one of these signals went high at any given time, you would use "if(~rst_n)" instead of "always".
 In the first part of this block, we're setting up some variables for our FSM: state - This variable stores what type of light we're currently analyzing; next_state - This variable stores what type of light we'll be analyzing in 1 second; count - This variable keeps track how many times each light has been analyzed so far; and count_delay - This variable keeps track how long it takes between each analysis.
 The code is a simple FSM (Finite State Machine) that will toggle the state of the light_highway and light_farm outputs based on the input signal, clk.
 The output signals of lights are connected to an AND gate which is controlled by a clock enable signal.
 The clock enable signal is generated by another FSM with its own state machine.
 The first FSM generates a 1s delay before it starts controlling the next state machine's output signal, which in turn controls the output signals of lights.
 The code starts with a case statement that checks if the current state is HGRE_FRED.
 If it is, then the next state will be HRED_FYEL.
 Otherwise, the next state will be HGRE_FRED again.
 The code starts by setting light_highway to 3'b100 and light_farm to 3'b010.
 The RED count en variable will start at 0 and YELLOW count en1 will start at 0 as well.
 Next, there are two if statements that check for delay3s2 and turn green on highway or red on farm road depending on which one comes true first: if(delay3s2) next_state = HGRE_FRED; // turn green for highway, red for farm road else next_state =HRED_FYEL; endcase
 The code will cycle through the states of red, yellow and green.
 The code attempts to be used in a situation where there are two different types of roads that need to be distinguished.
 The code will cycle through the states of red, yellow and green.
 The code attempts to be used in a situation where there are two different types of roads that need to be distinguished.
 The code starts by declaring two variables, RED_count and YELLOW_count.
 These are the counts of red and yellow delay values respectively.
 The code then declares a variable called count_delay which is used to keep track of how many clock cycles have passed since the last time it was incremented.
 The first line in the code sets up an always block that will be executed every time there is a rising edge on clk (the 1s clock enable).
 This always block increments count by one, but only if both RED_count and YELLOW_count are true.
 If either one or both of these conditions aren't met, then this line won't execute at all.
 The next three lines declare what happens when each condition is met: If RED_count or YELLOW_Count are true, then count will be increased by one; otherwise it remains unchanged.
 If both conditions are true, then count will be increased by 10; otherwise it remains unchanged again.
 Finally if just one condition is true (either RED or YELLOW), then count will be increased by 3; otherwise it remains unchanged again as well
 The code is a simple example of how to create a clock enable.
 The code above will count up by 1 each time the clock edge occurs and then it will reset back to 0.




## RTL Code

Proper File has been uploded.

### RTL Schematic View

[RTL Schematic View](That has been uploded in files.)


## TESTBENCH
Proper file has been uploded.

## Output Waveforms


It has uploded in file. that can reffer.


## Result

In this model we have observed various stages which describes about every signals. For example, Consider that at first stage (north-south end) signals gives some indication. 
Then, the signal is red that means signal at east-west side gives a green indication and traffic moves to their respective direction. Then after some delay yellow signal is 
obtain at east-west side and after the red signal arrives at the same time at the north-south end red signal goes off and green signal gets on and traffic moves to their 
particular direction. In this way process continues in the loop every day. 

The modern ways of multi-way traffic management improves the traffic condition up to a large extent. Traffic intensity is sensed and accordingly time is allotted for traffic to
pass. Verilog HDL is used to circuit description, code is generated which is simulated using Xilinx14.5.

This traffic light control system works on the concept of fixed time allocation at each side of the junction which cannot be changed as per varying traffic density. 
Timings allotted at every junction are fixed. Sometimes higher traffic density at one side of the junction demands longer time duration for green signal compared to the 
standard allotted time.

Thus, traffic light control system helps to conduct orderly flow of vehicles. There are lot many issues of obstacles, high level accidents which occurs every day. 
So, traffic signal controller prevents such occurrences. Still many areas or small towns don’t have the traffic light control facilities. And thus, many accident problems occur 
at those areas. Therefore, it is a primary purpose to have such facility in order to control and maintain the area.


## Future Work

This project can be enhanced in such away as to control automatically the signals depending on the traffic density on the roads using sensors like IR detector/receiver module 
extended with automatic turn off when no vehicles are running on any side of the road which helps in power consumption saving. 

A lot of development ideas for work in future can be implemented, such as using solar energy (independent power supply, i.e. saving the power). Using the GPRS map as an 
additional step for development and choosing the best road for the emergency and police vehicles. For national highways we can also design the 8 road traffic light controllers.


## References

1) Laboratory Exercise #12, The Traffic Light Controller Lab. “ECEN 248: Introduction to Digital Design”. Department of Electrical and Computer Engineering Texas A&M University.

2) Rajeev Madhavan, Verilog HDL Reference Guide, Automata Publishing Company, CA, 1993. ISBN 0-9627488-4-6

3) E. Sternheim, Rajvir Singh, Rajeev Madhavan, Yatin Trivedi, Digital Design and Synthesis with Verilog HDL, Automata Publishing Company, CA, 1993. ISBN 0-9627488-2-X

4) https://intentswell.blogspot.com/2021/03/traffic-light-controller-project-report.html

5) https://www.semanticscholar.org/paper/An-Advanced-Traffic-Light-Controller-using-Verilog-B.-ala/1ca8a8e50c2c8273a3ee1247a6057f8eb4f402ee

6) https://www.academia.edu/21200096/DESIGN_AND_IMPLEMENTATION_OF_TRAFFIC_LIGHTS_CONTROLLER_USING_FPGA_A_Project_Based_Laboratory_Report_in_partial_fulfilment_for_the_award_of_III_IV_B_Tech_I_Semester_Submitted_by_Lab_Instructor

7) https://vlsicoding.blogspot.com/2013/11/verilog-code-for-traffic-light-control.html 

8) https://www.fpga4student.com/2016/11/verilog-code-for-traffic-light-system.html 

9) https://www.slideshare.net/UtkarshDe/four-way-traffic-light-conrol-using-verilog 


## Author

- [Navinya](https://github.com/navinyagajare), Third year Engineering in Electronics and Tele Communication Engineering, Lokmanya Tilak College Of Engineering.

   
