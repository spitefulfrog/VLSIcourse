<h1>DAY 1:</h1>

Start of by merging the LEF and TLEF files for the picorv32a cpu

![image](https://github.com/user-attachments/assets/7b75380f-12ff-46ad-9e9c-784c96725919)

then run the sythesis using the 'run_sythesis' command.

![image](https://github.com/user-attachments/assets/816bf3b0-0112-412a-93ce-46f784149c2a)

flip ratio = no. of dflops/no of cells = 1613/14876 
<h3>approx. = 10.84297%</h3>
<h1>DAY 2:</h1>

<h2>viewing the floorplan:</h2>

After running the floorplan using the 'run_floorplan command', it can be viewed using a piece of software called magic.

Magic required 3 paths to be given, the path for the .tech file, the .lef file for the same chip and the .def file

the command, for the picorv32a, with the sky130 PDK is this:

Attatched below is the graphiccal view of the picorv32a microcontroller using magic:

![image](https://github.com/user-attachments/assets/7fad648a-6d9d-42af-8acb-e99f32a2849b)

<h1>DAY 3:</h1>

<h2>Using SPICE software to simulate your circuit:</h2>

Using magic, a spice file can be extracted, and here are the commands to be entered in magics tkcon window to do so:

<ul>
  >extract all
  >ext2spice cthresh 0 rthresh 0 (Can be ignored. Adds extra details)
  >ext2spice 
</ul>

To SPICE simulate the dezired circuit, a few modifications must be made, and those are:

<ul>
  >Include the technical specification of the used components, which in this case are the PMOS and NMOS transistors.
  >Power the entire circuit, which in this case was done by creating a 3.3 volt power supply called 'VSS' and a ground called 'VDD'
  >Pulse the inputs of the transistors 
</ul>

Here is the .spice file with the changes included:

![image](https://github.com/user-attachments/assets/20f8efcb-bda4-4069-bdee-d8eec1e28192)

<h3>Running the SPICE simulation</h3>

To invoke the ngspice software, type the following in your terminal :
<ul>
  >ngspice 'your file's name.spice'
</ul>

After that, to plot the output and input vs time, type the following in the ngspice terminal:

<ul>
  >plot  vs time a
</ul>

here is the screenshot of the same:

![image](https://github.com/user-attachments/assets/037ac3a1-0044-4588-8b7a-ec3daa822691)


<h3>Analysis of circuitry</h3>

<h4>Rise time:</h4>
Is the difference between times of 20% rise of the y axis and 8-% rise of the y axis.
<h4>Cell rise delay</h4>
Is the difference between the 50% of the  input and the 50% of the output

<h1> Day 3:</h1>
<h2>Converting a mag file into a lef file:</h2>

LEF files contain only as many detailsas required for placement and routing, and are more universl compared to .mag files, used only by magic, which is why LEFs are prefered over other formats.

The following should be types in order to convert a mag file into a lef file:

<ul>
  >lef writeall
</ul>

<h2>Modifying the openlane flow:</h2>
The openlane flow can be modifies by changing the config.tcl file for that design.I will be including a renamed version of the standard skyrc inverter. To do so, you need to add the renamed inverter file and its associated part files using the syntax shown in the screenshot:

![image](https://github.com/user-attachments/assets/c71611bf-7fb4-4f31-970d-a6c9e7bcc065)

and in the during the synthesis process, you will see that your inverter with your filename will be included,as seen in the 3rd line of the terminal in the given screenshot:

![image](https://github.com/user-attachments/assets/d63d618e-cbb8-4e32-82b9-df162d350250)
