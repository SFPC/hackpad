# HDL/FPGA

Instructor [](http://www.moeller.io/)http://www.moeller.io/

 CHI paper

visual hole

coming from LED

to create hardware without actually manufacturing

program software to deliver hardware 

Freesoc

arduino- more open to the community, cypress- PSoC - for professional developers

You are designing hardware and software

Making virtual gates: actually real gates thats getting synthesized.

when you connect things together, takes block diagrams, connects all the modules and synthesize the machine

control counters with digital logic 

datasheets to hardware 

APIs you can call from the C code

Create PWM, interrupts 

Configure the intterupt, output / any of the events that happen

allow you to create flexible hardware with block diagrams

**Whats the deal with C code?  **

Create three integers 

assign the values 

making a program.

Device name ends in LP309 

Assembly language 

C code is an abstraction

compiled in to assembly- 

that is executed in the machine 'thats CPU 

cpu is an interesting piece of hardware. 

What is hardware?

the base of cpu is ALU. 

Add, 

Machine that runs code

reducing what you've written in to what machine could understand

Data path.

takes aseembly code and deos somethign with it

instruction is called in instruction memory

the data

addresses that are five bit wide. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_OCWcmSQVwvz_p.77239_1418323304111_undefined)

you are not wrtiging machien code. you are writing with abstraction. 

Assembly is another abstraction, instruction for hardware that exists in the real world

hardware is another abstraction, becasue one and zero don't exist, they are representation of electrical signal.

java- something that interprets code that interprets code that interprets code

you know how to write abstractions for the machines, 

we can build an ALU from block diagram

netlist

into verilog file 

if you are using FPGA, xilinx tools, some are better than others 

add a component

symbol wizard 

Terminal for control part 

tie things together

once you created new component,

generate verilog

cheat sheet 

[](https://www.dropbox.com/s/fjg7iz1obzs5awy/verilogcheatsheet.pdf?dl=0)[https://www.dropbox.com/s/fjg7iz1obzs5awy/verilogcheatsheet.pdf?dl=0](https://www.dropbox.com/s/fjg7iz1obzs5awy/verilogcheatsheet.pdf?dl=0) 

Tell verilog what these inputs are

wire - is driven by another signal 

register - typically output, storing state, data, 

two bit wire. 

wire [1:0] CNTRL; 

Most significant bit and least significant bit

Assign statement- you can't assign to register 

massively parallel

what's inside of fpga

cells- look up table 

inputs codified - maps them to specific values and the outputs 

6 inputs and outputs 

2 to the 6 times 2 ooutputs 

2 input mux 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_OCWcmSQVwvz_p.77239_1418324171949_undefined)

convulted way of making logic

but taking abstraction and reducing to hardware 

create paramenter 

4 different parameters for control 

we want it to be A and B only if control is AND 

if control is equal to AND, then we will set Q to A and B, 

when you are building hardware, what you care of is clock

processor runs on clock, I2C

EVERYthing runs on clock 

always statement 

not using typical equal sign

non blocking assignment 

everything thats non blocking happens simultaneously

you can do conditional

synchronous 

clocks to state machines

case statements 

clock speed inside . 60 mg hz

outside 30 m hz

each time value passes through, you have propagation delay.

**FSM **

the key element to any sequential logic- state machines

FSM 

instructions are laid the machine generates output 

output is the new state

memory of the variable is the state of the machine 

HDL is building hardware.

C- code is working within state machines

if this room was a computer, this would be state machine

 if i move my chair, the state would have changed

 i don't nee to worry about the physucal things \

 programming is totally abstract level

 hardware- you need to define the state space. 

 computational state space-  anytthing is possible

 where as, in our state machines, we need to define what the states are 

 state machines consists of inputs, outputs and number of states

  drawing as bubbles 

  transtitions are drawn as arrows 

we start at state one

will do one or two things

j - 0, j

our inputs int he state mahine defines transition

output K

[](http://cs.stackexchange.com/questions/16315/difference-between-a-turing-machine-and-a-finite-state-machine)http://cs.stackexchange.com/questions/16315/difference-between-a-turing-machine-and-a-finite-state-machine

FSM - Turing Machine

PID oven

funny thing about computers

data path we had is a FSM.

limited amount of memory and states in which computers can be in.

[](https://www.twistedtraces.com/)https://www.twistedtraces.com/

[](https://www.eewiki.net/display/microcontroller/Getting+Started+with+PSoC+4+Prototyping+Kits+-+CY8CKIT-049)https://www.eewiki.net/display/microcontroller/Getting+Started+with+PSoC+4+Prototyping+Kits+-+CY8CKIT-049