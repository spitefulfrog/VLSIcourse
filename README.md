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
