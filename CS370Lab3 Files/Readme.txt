Lab3 - README.txt

Jacob Romio - 822843795
	Part 1:
	- Assisted in planning to gain optimized equations for implementation
	- Implemented optimized equations into Gotcha Anti Theft part
	- Implemented buttons for user input

	Part 2:
	- Assisted in initial planning for parts selection and design
	- Built user programmable code part

	
Jack Bruce - 822320220
	Part 1:
	- Assisted in planning to gain optimized equations for implementation
	- Implemented 4-bit Incrementer for "Shut Off" part

	Part 2:
	- Assisted in initial planning for parts selection and design
	- Built 8-bit Sequencer part

====================================================================================

Files contained in JRomio.zip:

Factory Preset Model.cct
	- part 1 main circuit

User-Programmable Model.cct
	- part 2 main circuit

Project3.clf
	- library file containing helping parts
		+ 8-Bit Sequencer
		+ Gotcha Anti-Theft
		+ Programmable User Code
		+ Shut Off (aka 4 Bit Incrementer.cct)
		+ SR Latch

4 Bit Incrementer.cct		
	- main component of "Shut Off" part
	- tracks the number of button presses and locks the user out after 16
		incorrect presses
	- reset input resets incrementer to 0

8-Bit Sequencer.cct
	- uses an 8-bit shift register to track the 8 most recent input bits
	- implemts "Shut Off" part to lock user out after 16 incorrect presses	

Gotcha Anti-Theft.cct
	- main component of part 1 circuit
	- 8 bit sequence recognizer built to recognize 01100111 from user input
		+ ouputs 1 for success
		+ outputs 0 otherwise (this includes locked state)
	- locks user out after 16 incorrect button presses

Programmable UserCode.cct
	- uses an 8-bit parallel loading register to accept a custom 8-bit code
		from D0:D7 and compares these bits with with the most recent
		8-bits entered by user from A0:A7
	- E ouputs 1 when most recent 8-bits match custom code, outputs 0 otherwise
	- only loads new code when ENTERCODE input = 1

SR Latch.cct
	- used in "Shut Off" part for level triggered storage

====================================================================================

Planning:
	- Part 1: 
		1. Made state diagram for 8 bit sequence recognizer
		2. Made state table with information gained from state diagram
			- planned for 4 D-flip flops (3 to handle 8 bit sequence,
				1 to handle user input)
		4. Made K-map for each flip flop
		5. Obtained OPTIMIZED equations for each flip flop from K-Maps
		6. Implemented equations as logic circuits in Logic Works
		7. Added extra components for additional features specified in prompt

	- Part 2:
		With the new knnowledge of how registers work part 2 required little planning
		1. Store most recent 8 bits in shift register
		2. Store custom code in another register
		3. Compare input register with code register, and output 1 if bit sequences match.