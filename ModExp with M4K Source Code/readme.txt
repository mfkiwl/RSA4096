4096-bit RSA module on Altera Cyclone II EP2C50

The implementation follows ModExp4096.pdf. 

Interface Control Document is in interface control document folder;
FPGA image and summary reports are in final output_files folder;


1. How to compile?
	1.1. Need nMem.mif, mMem.mif, eMem.mif, rMem.mif, tMem.mif, nprime0Mem.mif as the memory initialization files; You can follow the example format to create your own test files;
	1.2. Create a project in Quartus ii 12.1sp1 web version, choose Cyclone ii EP2C50 device;
	1.3. Add _parameter.v, ModExp.v, mul_add.v, n_mem.v, e_mem.v, t_mem.v, r_mem.v, m_mem.v, res_mem.v to this project;
	1.4. Follow compile configuration.txt to set up compilation settings;
	1.5. Click Assignments -> TimeQuest Timing Analyzer Wizard; click Next; add clk to Input Pin, set a Period such as 1ns; Click Next until Finish;
	1.6. Click Processing -> Start Compilation. It takes about half an hour to finish compilation (because too many code and optimization);


2. How to simulate?
	2.1 After compilation, click Tools -> Run Simulation Tool -> RTL Simulation. The ModelSim-Altera will pop out;
	2.2 Copy nMem.mif, mMem.mif, eMem.mif, rMem.mif, tMem.mif, nprime0Mem.mif, ModExp_tb.v, ModExpSimulation.tcl to ~\simulation\modelsim folder;
	2.3 In ModelSim script window, write: do ModExpSimulation.tcl; the simulation starts and wave graph will pop out!


3. Where is the FPGA image and the summary report?
	If you recompiled, it is in output_files folder. If not, we have a copy in folder: My Final Output_files.




Enjoy!

	by Qin ZHOU: qinzhou@cs.ucsb.edu
		Please email me if you have any questions.