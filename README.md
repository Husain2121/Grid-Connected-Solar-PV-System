# Grid-Connected-Solar-PV-System

## What was built
A model of a simulated solar arrays that is connected to the grid.

## How it works
Solar Array and Capacitor
As in a typical solar setup, we have a solar array with inputs for temperature and irradiance. Connected in parallel is a capacitor which helps protect the other components by reducing ripples in the DC output.

Boost Converter with MPPT
The solar array is connected to a boost converter that steps up the DC voltage to the required level. To make this process efficient, an MPPT (Maximum Power Point Tracking) algorithm (written in MATLAB code) is connected. Its purpose is to continuously extract the maximum possible power from the solar panels.

Perturb and Observe Method (P&O):
This method works by slightly shifting the operating voltage and then observing the change in power:

If power increases, we keep moving in the same direction (to the right on the PV curve).

If power decreases, we reverse the direction (to the left on the PV curve).
Over time, this allows the system to lock onto the Maximum Power Point, where the solar panels deliver their best performance.

Three-Phase Inverter
The boosted DC voltage is then fed into a three-phase inverter. Since the grid operates using three-phase AC, this step is essential. The inverter converts the DC into AC with the correct number of phases.

Phase-Locked Loop (PLL)
Because we are grid-connected, synchronization is critical. A Phase-Locked Loop (PLL) system ensures the inverter’s output matches the grid’s frequency and phase. It uses a feedback loop to constantly adjust the output so that both are in sync, which is necessary for safe and stable grid connection.
