Download Link: https://assignmentchef.com/product/solved-ece383-lab-4-mplab-introduction-and-pic24-assembly-language
<br>
<em>Goals: The goals of this lab are to introduce students to basic PIC24 assembly language, usage of the MPLAB Integrated Development Environment (IDE) and associated tools.</em>

<h1>1.     Introduction</h1>

This lab introduces the Microchip MPLAB Integrated Design Environment. All files referenced in the lab are assumed to be in <em>C:microchipchap3. </em>The tasks in this lab are:

<ul>

 <li>Use MPLAB             to         simulate          the       PIC24   assembly         language         program   in         the</li>

</ul>

<em>C:microchipchap3mptst</em><em>_</em><em>word.mcp </em>project to become familiar with the MPLAB environment.

<ul>

 <li>Implement some simple programming tasks using PIC24 assembly language.</li>

</ul>

This lab requires you to capture portions of the screen. The lab computers use the Windows operating system. This includes the “Snipping Tool” that may be used to capture portions of the screen. Other third party tools are also available.

As always, read through the entire lab and scan the supplied files before starting work. The reporting requirements have you verify computations performed by the assembly language program. In all cases, make it easy for the TA to verify your computations by showing your work. <strong>NOTE</strong>: When writing MPLAB assembly language programs, do not use variable names <strong>a </strong>or <strong>b </strong>as these are reserved names. All hand calculations requested should be shown on a separate piece of paper in the lab report.

<h1>2.     Pre-lab</h1>




<strong>For this lab assignment</strong>, Task1 and Task 2 should be completed as a pre-lab assignment prior to your assigned lab time. You may also complete all the tasks (including Task 3 and Task 4) prior to the lab time. This may reduce your time in the lab, but is not required.




<strong>TA check: As soon as you enter lab, provide the TA with a pre-lab report that includes the complete assembly language programs. Lab time will be devoted to debugging the program execution and correcting any errors within MPLAB noted by the lab instructor. Make sure your group member names and date are on the pre-lab report.</strong>




<h1>3.     TASK 1: MPLAB Introduction</h1>




Perform the following steps:




<ul>

 <li>Copy the files in <em>C:microchipchap3 </em>to a suitable directory on your network drive or hard disk. Make sure the directory you use has no spaces in the directory path. An example of a good directory name to</li>

</ul>

use would be <em>C:tempusername </em>where “username” is your unique login name.

<ul>

 <li>Start the MPLAB IDE. Use Project-&gt;Open and open the <em>mcp </em>project located in your directory.</li>

 <li>Use <em>Configure-&gt;Select Device </em>to select the PIC24HJ128GP502 device for your processor.</li>

 <li>Use <em>Project-&gt;Build All </em>(Ctrl+F10) to assemble the program. If the source file is not already open, double- click on the <em>s </em>source file to open it.</li>

 <li>After the project is assembled, use <em>View-&gt;Program Memory </em>and open the program memory window. Scroll the window until you find your program in memory. This should start at location 0x204.</li>

 <li>Use <em>View-&gt;File Registers </em>to view data memory. Scroll to location 0x800, which is where your variables will start.</li>

 <li>Use <em>View-&gt;Special Function Registers </em>to view the special function registers (W0-W15, etc.).</li>

 <li>Open a watch window <em>(View-&gt;Watch) </em>and use <em>Add Symbol </em>and <em>Add SFR </em>to watch variable values and special function register values, respectively, of the <strong>i</strong>, <strong>j</strong>, <strong>k </strong>variables and the <strong>W0 </strong>(WREG0) special function register.</li>

 <li>Use <em>Debugger-&gt;Select Tool-&gt;MPLAB Sim </em>to select the MPLAB Simulator.</li>

 <li>Use <em>Debugger-&gt;Step Over </em>(F8) to single step the program. Watch both the memory locations and watch window locations, and correlate their changing values with the instructions being executed.</li>

</ul>




<strong>TA check: Show the TA the task 1 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source assembly language program in your lab report</strong>.




Modify the avalue equate (statement <strong>.equ avalue, 2047</strong>) to be the last four digits of your student ID. Reassemble the program and re-simulate it. Take a screen shot of both the Watch window contents and the memory window contents. In your report, you must show calculations that verify the screen shot values match the expected result (note, avalue is in decimal, as are the <strong>last four digits of your student ID</strong>: the values displayed in the file registers window are in HEX).




<strong>TA check: Show the TA the modified task 1 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source assembly language program in your lab report</strong>.




<h1>4.     TASK 2: myadd.s</h1>




Use <em>Project-&gt;Save Project As </em>and save the <em>mptst_word </em>project as a new project named <em>myadd</em>. Save the <em>mptst_word.s </em>file as <em>myadd.s</em>. Right-click on the <em>mptst_word.s </em>file in the left-hand workspace window and use the <em>Remove </em>option to remove it from the <em>myadd </em>project. Right click on the <em>Source Files </em>and use <em>Add Files </em>to add the   <em>myadd.s   </em>file   to   the   project.   Edit   the   <em>myadd.s   </em>file   and   remove all   of   the   instructions   from <strong>mov #avalue, W0 </strong>through <strong>mov WREG,k</strong>. You can now use this file as a start for a new program.




Your CWID student number is an eight digit number Y<sub>7</sub>Y<sub>6</sub>Y<sub>5</sub>Y<sub>4</sub>Y<sub>3</sub>Y<sub>2</sub>Y<sub>1</sub>Y<sub>0</sub>. For this task we will consider this to be an eight digit hexadecimal number.




Write a program to add the four digit hex number formed by 0xY<sub>3</sub>Y<sub>2</sub>Y<sub>1</sub>Y<sub>0 </sub>to the four-digit hex number formed by

<u>0xY<sub>7</sub>Y<sub>6</sub>Y<sub>5</sub>Y<sub>4</sub>. Reserve space for two 16-bit variables in data memory named <em>lsp </em>and <em>msp </em>to hold the hex values </u>0xY<sub>3</sub>Y<sub>2</sub>Y<sub>1</sub>Y<sub>0 </sub>and 0xY<sub>7</sub>Y<sub>6</sub>Y<sub>5</sub>Y<sub>4 </sub>respectively. Reserve space for a variable named <em>sum </em>to hold the sum of <em>lsp </em>and <em>msp.</em>




The following C code describes the program. You must translate each line of the C program to corresponding assembly instruction(s).




uint8 aa=100, bb=22; uint16 lsp, msp, sum;




lsp = 0xY3Y2Y1Y0;       // Four digits of CWID treated as hex msp = 0xY7Y6Y5Y4;       // Four digits of CWID treated as hex sum = lsp + msp;




sum = sum + aa + bb;




Use the watch window to watch variables <em>aa, bb, lsp</em>, <em>msp</em>, and <em>sum</em>. Also, use the data memory window to monitor the memory locations corresponding to these variables.




<strong>TA check: Show the TA the task 2 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source assembly language program in your lab report. Since you will be working in teams in the lab, use only one student number for each team. </strong>

<strong> </strong>

<h1>5.     TASK 3: mysub.s</h1>







Create a project named <em>mysub </em>using the same procedure given in Task 2 (<em>Project -&gt;Save Project As</em>, etc.) corresponding assembly language file named <em>mysub.s</em>. Using digits Y5Y4Y3Y2Y1Y0 from your student ID, write an assembly language program that implements the following C program. You must translate each line of the C program to assembly instruction(s).

uint16 xx=0xDEAD, yy=0xBEEF;

uint8 i, j, k, l, m;




i = Y1Y0; j = Y3Y2; k = Y5Y4; l = i + k; m = j – l; xx=xx-yy-m;




Variables <em>i</em>, <em>j</em>, <em>k</em>, <em>l</em>, <em>m </em>are all 8-bit (byte) variables and xx and yy are 16-bit variables.  Y1Y0, Y3Y2 and Y5Y4 are considered as decimal numbers for this task.  Use the watch window to watch variables <em>i</em>, <em>j</em>, <em>k</em>, <em>l</em>, <em>m, xx, </em>and <em>yy</em>. Also, use the data memory window to monitor the memory locations corresponding to these variables. Write your program, simulate it, and verify that you calculate the correct results.




Hint: If you experience the error “Link Error: Cannot access symbol (xx) at an odd address”, initialize 16-bit variables first and then 8-bit variables. That is, all variables defined using the <em>.space 2</em> directive should appear before variables defined using the <em>.space 1</em> directive.







Give the value of the flags after the execution of each instruction. Assume that <strong>W0 = j and W1 = l</strong>.




<table width="729">

 <tbody>

  <tr>

   <td rowspan="2" width="205"><strong>Instruction </strong><strong> </strong></td>

   <td width="131"> </td>

   <td width="84"> </td>

   <td colspan="2" width="179"><strong>Value of flags </strong></td>

   <td width="131"> </td>

  </tr>

  <tr>

   <td width="131"><strong>C </strong></td>

   <td width="84"><strong>Z </strong></td>

   <td width="47"> </td>

   <td width="131"><strong>OV </strong></td>

   <td width="131"><strong>N </strong></td>

  </tr>

  <tr>

   <td width="205">ADD.B W0,W1,W0</td>

   <td width="131"> </td>

   <td width="84"> </td>

   <td width="47"> </td>

   <td width="131"> </td>

   <td width="131"> </td>

  </tr>

  <tr>

   <td width="205">SUB.B W0,W1,W0</td>

   <td width="131"> </td>

   <td width="84"> </td>

   <td width="47"> </td>

   <td width="131"> </td>

   <td width="131"> </td>

  </tr>

 </tbody>

</table>




<strong>TA check: Show the TA the task 3 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source assembly language program in your lab report</strong>.




<h1>6.     TASK 4: mylogicops.s</h1>




Create a project named <em>mylogicops </em>using the same procedure given in Task 2 (<em>Project -&gt;Save Project As</em>, etc.) corresponding assembly language file named <em>mylogicops.s</em>. Write an assembly language program that implements the following C program. You must translate each line of the C program to assembly instruction(s).




uint8 u8_a, u8_b, u8_c, u8_d, u8_e, u8_f; uint16 u16_x=0x0001;




u8_a=0xAF; u8_b=0x50;




u8_c= u8_a &amp; u8_b; u8_d= u8_a | u8_b; u8_e= u8_a ^ u8_b; u8_f=~u8_a;

u16_x=~u8_d | (u16_x &amp; u8_c);




Use the watch window to watch variables <em>u16_x, u8_a, u8_b, u8_c, u8_d, u8_e, </em>and <em>u8_f</em>. Also, use the data memory window to monitor the memory locations corresponding to these variables. Write your program, simulate it, and verify that you calculate the correct results.




In addition to simulating your program within MPLAB, you must download your program to your PIC24 hardware (the Microstick II) and demonstrate the execution of your program on hardware to the TA. Make sure the Microstick II development board is attached to a USB port on your computer and make sure the slider switch on the board is set to position A. With the <em>mylogicops </em>project open, use the following steps




<ul>

 <li>If not already selected, use <em>Configure-&gt;Select Device </em>to select the PIC24HJ128GP502 device for your processor.</li>

 <li>Use <em>Debugger-&gt;Select Tool-&gt;Starter Kit on Board </em>to select the Microstick II as the target. You should see messages in the MPLAB Output window indicating a successful connection to the Microstick II board.</li>

 <li>Use <em>Project-&gt;Build All </em>(Ctrl+F10) to assemble the program. If the source file is not already open, double- click on the <em>s </em>source file to open it.</li>

 <li>Use <em>Debugger-&gt;Program </em>to download your code to the Microstick II. You should see messages in the MPLAB Output window indicating successful programming of the Microstick II board.</li>

 <li>After the project is downloaded, use <em>View-&gt;Program Memory </em>and open the program memory window.</li>

 <li>Scroll the window until you find your program in memory. This should start at location 0x204.</li>

 <li>Use <em>View-&gt;File Registers </em>to view data memory. Scroll to location 0x800, which is where your variables will start.</li>

 <li>Use <em>View-&gt;Special Function Registers </em>to view the special function registers (W0-W15, etc.).</li>

 <li>Open a watch window <em>(View-&gt;Watch) </em>and use <em>Add Symbol </em>and <em>Add SFR </em>to watch variable values and special function register values, respectively, of the all of the defined variables and the <strong>W0 </strong>(WREG0) special function register.</li>

 <li>Set a breakpoint on the first line of your assembly language program by double clicking on the line in the assembly language program.</li>

 <li>Begin the execution of your program by selecting <em>Debugger-&gt;Run</em>.</li>

 <li>Use <em>Debugger-&gt;Step Over </em>(F8) to single step the program. Watch both the memory locations and watch window locations, and correlate their changing values with the instructions being executed.</li>

</ul>




<strong>TA check: Show the TA the task 4 results including the final state of the program, data memory, and the watch window for both the MPLAB PIC24 simulator and the PIC24 hardware. Use a screen capture tool to capture these windows and include them in your lab report. Include your source assembly language program in your lab report. </strong>


