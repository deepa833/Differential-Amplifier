# Differential-Amplifier
i . Aim:
Design and analyse the differential amplifier for the following specifications:

A MOS Differential Amplifier is a key circuit in analog electronics, used for signal amplification, common-mode rejection, and noise suppression. It consists of two matched MOSFETs, a current source, and load resistors.

Circuit Diagram:![Screenshot 2025-03-14 082051](https://github.com/user-attachments/assets/09b17eea-0907-4799-b1c4-3c7b73f6f716)


Working Principle

Differential Input: The circuit amplifies the difference between the two input voltages (V_IN1 - V_IN2).
Current Source Biasing: The total bias current (I_BIAS) is constant, ensuring stable operation.
Output Voltages: The amplified signals appear at V_OUT1 and V_OUT2. lab2
![Screenshot 2025-03-14 082115](https://github.com/user-attachments/assets/0aca87e0-7898-488b-8f94-162e53b8db11)

The sum of the two drain currents ID1 and ID2 must equal IBIAS. We also know that the two drain currents are equal because, in this idealized analysis, both halves of the circuit are identical. Thus,

![Screenshot 2025-03-14 082130](https://github.com/user-attachments/assets/dbe9fb1a-10f5-4eb4-8a18-45068bb06d4e)


Let’s assume for the moment that the transistors are in saturation. The equation for saturation-mode drain current is the following: ![Screenshot 2025-03-14 082143](https://github.com/user-attachments/assets/125a43a7-91dc-41da-9028-918023109329)


The drain current is already established (by the current source) and the gates are tied to the ground node; this means that the source voltage will settle on whatever value creates a gate-to-source voltage (VGS) corresponding to a drain current of IBIAS/2.

Components used:
NMOS Transistor
Voltage Source
Resistors
Ground
CONNECTING wires
Procedure:
• Open LTspice and create a new schematic by selecting File > New Schematic.

• Select the Components required to design a Common Source Amplifier such as NMOS,voltage source, wire, and ground.

• Connect the components as shown in the above fig.1

• Set Component Values by Right-clicking on each component to set their values

• Go to edit option select spice directive and attach tsmc018.lib file

• To run the simulation click on run button

• To get DC Operating Point Analysis

Click on Simulate > confiure analysis
Select DC op pnt and click OK
Place the .op directive on your schematic and stop time as 3m
Run the Simulation
Click the Run button (the running man icon)
The DC operating point voltages and currents will be displayed in a table
• To get AC operating Point analysis

Right-click on the voltage source and select sine function set AC Amplitude to 50mv, frequency to 1KHz, DC offset to 1v
Click on Simulate > configure analysis
Select AC Analysis.
Enter the type of sweep decade, number of points 20, start frequency 0.1 Hz, and stop frequency 1T Hz.
Click OK and place the .ac directive on your schematic.
Run the Simulation
Click the Run button
The AC analysis results will be displayed to get the waveform click on input/output voltage.
• To get Transient Analysis

Click on Simulate > configure analysis
Select Transient and enter the stop time (5milliseconds).
Click OK and place the .tran directive on your schematic.
Run the Simulation:
Click the Run button.
The transient analysis results will be displayed to get waveform click on output /input volatges.
circuit 1:(with RSS)
