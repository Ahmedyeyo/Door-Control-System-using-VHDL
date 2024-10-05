Door Control System using VHDL

Project Overview
This project implements a door control system in VHDL. The system controls a door's operations using a state machine. It transitions between different states such as open, closed, locked, and handles error conditions when invalid operations are performed. The project was simulated using ModelSim and validated on an FPGA board (DE10-Lite).

Key Features
Four buttons (KEY_0 - KEY_3) are used for controlling the door operations.
KEY_0: Close the door
KEY_1: Open the door
KEY_2: Lock the door
KEY_3: Unlock the door
State transitions between open_state, closed_state, locked_state, and error_state.
LED indicators:
LEDR_0: Indicates the door is open.
LEDR_1: Indicates the door is closed.
LEDR_2: Indicates the door is locked.
LEDR_ERR: All LEDs light up in case of an error state.
Error handling: Invalid operations, such as locking an open door, trigger the error state.
States and Transitions
open_state: The door is open.

Transition to closed_state when KEY_0 is pressed.
Transition to error_state if locking/unlocking is attempted while the door is open.
closed_state: The door is closed.

Transition to open_state when KEY_1 is pressed.
Transition to locked_state when KEY_2 is pressed.
locked_state: The door is locked.

Transition to closed_state when KEY_3 is pressed (unlock).
error_state: Invalid operation detected, such as locking an open door.

All LEDs turn on to indicate the error.
VHDL Structure
The project follows a behavioral architecture with signals and processes designed to handle button synchronization and state transitions.

Key VHDL Files
door_control.vhd: The main VHDL file defining the state machine and controlling logic.
Simulation & Testing: The system was thoroughly tested using ModelSim to ensure correct state transitions and error handling.
How to Run
To test the system on an FPGA:

Load the VHDL code onto the DE10-Lite FPGA board.
Connect the push buttons to control the door state as described above.
Observe the LED indicators to monitor the current door state and error conditions.
