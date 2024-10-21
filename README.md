
# Flight Simulator

This is a simple flight simulation program that uses basic physics principles to simulate flight dynamics. It is implemented in C and utilizes the X11 library for graphical rendering.

## Features

- Real-time flight dynamics simulation.
- Keyboard input to control pitch, roll, and yaw of the simulated aircraft.
- Graphical rendering using X11 for trajectory visualization.

## Prerequisites

- **X11**: The code relies on X11 for graphical output. Ensure you have the X11 development libraries installed.
  
  For Ubuntu/Debian:
  ```bash
  sudo apt-get install libx11-dev
Math Libraries: The math.h library is used for trigonometric functions in flight dynamics calculations.
Building the Project
To compile the code, use the following command:


gcc -o flight_simulator flight_simulator.c -lX11 -lm
This will compile the program, linking against the X11 and math libraries (-lX11 and -lm respectively).

Running the Simulation
Once compiled, the simulator can be run from the terminal:

./flight_simulator

## Controls
Up Arrow (↑): Increases pitch (nose up).
Down Arrow (↓): Decreases pitch (nose down).
Left Arrow (←): Rolls the aircraft left.
Right Arrow (→): Rolls the aircraft right.
Other Input: Adjusts flight variables (e.g., thrust, yaw rate).
The simulation window will display real-time changes to the flight dynamics, and the trajectory will be plotted based on the current control inputs.

## Simulation Dynamics
The flight simulator uses simplified physics to model the movement of the aircraft, including:

Roll: Rotation around the aircraft's longitudinal axis.
Pitch: Rotation around the aircraft's lateral axis.
Yaw: Rotation around the vertical axis.
Thrust and Drag: Affect acceleration and deceleration of the aircraft.
Lift: Generated based on the aircraft’s angle of attack and velocity.
Physics Update Cycle
The physics of the simulation are updated continuously within the main loop. Key equations involved include:

Angular Motion: Utilizes basic trigonometric functions (sin, cos) to calculate the new orientation of the aircraft.
Forces and Torques: Lift, drag, and thrust are calculated based on the aircraft’s current state, and they influence the resulting trajectory.
For each iteration of the loop, the aircraft's state (position, velocity, etc.) is updated based on the control inputs and the physics equations.

## Further Modifications
You can adjust various parameters in the code to simulate different aircraft behaviors:

dt: Time step for the simulation. Increasing this will speed up the simulation, while decreasing it will provide more precise (but slower) calculations.
mass, inertia, force: Adjust these parameters to simulate different aircraft weights, inertia, and thrust capabilities.
Rendering: Modify the XDrawLine and XDrawString functions to customize the graphical output.

## Known Limitations
The simulator does not account for more advanced aerodynamic effects such as induced drag, lift coefficients, or complex weather conditions (e.g., wind gusts).
The simulation uses a simplified flight model, so real-world behavior (e.g., stall, slipstream) may not be fully captured.
The graphical output is very basic and can be enhanced by introducing more sophisticated rendering techniques.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
