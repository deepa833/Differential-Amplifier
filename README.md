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

Design a differential amplifier for the following specifications Using LTSpice

- VDD (Supply) = 2.2 V

- P (Power Budget) = 1 mW

- VICM (Gate Voltage) = 1 V (Input)

- VOCM (Drain Voltage) = 1.1 V (Output)

- VP (Tail Voltage) = 0.4 V

Perform DC Analysis, Transient Analysis, Frequency Response and find out required parameters

We have performed some basic calculations based on our specification and the required parameters are listed below

- ISS = 1000 μA (Total Bias Current)
- ID1 = ID1 = 500 μA (Branch currents are equal due to symmetry of circuit)
- RD1 = RD1 = 1.9 kΩ
- RSS = 400Ω (Tail Resistance)
- Q point = (VDS = 0.85 V, ID = 500μA) @ VGS = 0.8 V
 PREREQUISITES

Before we start the analysis we need to set up the W and L paramaters of the mos transister, namely the wodth and the length. Let us first fix the lenght to 180nm and then by using the spice directive we can get the required value of the width so that the current is the same as the calculation.

![Screenshot 2025-03-07 121612](https://github.com/user-attachments/assets/866487d2-17bd-4999-970b-febfece28eb8)

So we got the value to be 6.417 μm for the width so that the q point is set properly.

Now we will go to the dc analysis

## DC ANALYSIS

![Screenshot 2025-03-07 122522](https://github.com/user-attachments/assets/b663351d-080f-43fa-adcc-68368f221e84)

For the better understanding the parameters across each mosfet. 

![Screenshot 2025-03-07 122439](https://github.com/user-attachments/assets/4636862f-9b01-49d6-8cf8-ce4d632f557a)

Here one thing to notice is the change in the Threshold value of the mosfet from 0.366V to 0.497V. This is due to the body effect.

Any increase in the input voltage will interfere with the Vp and also the current. In case we have put replaced the resistor with the current source, then we can only notice the change in the vp value.

## TRANSIENT ANALYSIS

![Screenshot 2025-03-07 124312](https://github.com/user-attachments/assets/7956f603-9892-4772-ae1c-a3347c1ca072)

We got the gain to be -2.7V/V. 8.62 in db. 180degree phase shit.

## AC ANALYSIS

![Screenshot 2025-03-14 193304](https://github.com/user-attachments/assets/dced33c6-8c0f-4c8f-b4d1-651e321fdfa2)


Now we can calculate dB gain using transient analysis

- dB gain (Theoretical) = 20 log(AV) = 8.62 dB
- dB gain (From graph) = 8.79 dB (close to theoretical value)
- -3dB gain = 24.437 GHz
- Bandwidth = 24.437 GHz

## CASE 2 : With Current Source

![Screenshot 2025-03-14 193743](https://github.com/user-attachments/assets/c16017ad-e56d-417e-b57e-9e02ba19385a)

## DC ANALYSIS

We have to give the current source the value of total current else it will violate the kirchoff's current law and will change the biasing of MOSFETs.

![Screenshot 2025-03-14 194059](https://github.com/user-attachments/assets/c6a436cb-88b3-415a-bcb3-ed3b72d881ff)

For the better understanding 

![Screenshot 2025-03-14 194222](https://github.com/user-attachments/assets/1dd6b5ca-d428-4350-8bd9-a9e5004b0921)

The DC Operating Point and other DC Parameters is exactly the same as in previous case however something very interesting happens when we increase the VICM to 1.1 V the operating point is still similar, MOSFETs are still in saturation region and we are still under our prescribed power budget thus this configuration increases operation stability

## TRANSIENT ANALYSIS

![Screenshot 2025-03-14 194728](https://github.com/user-attachments/assets/2220c132-4bcf-4c79-b2dc-1ee67cc7bc66)

Here we can see the gain has decreased to some extent i.e, from -2.7V/V to -2.0526V/V

This gain is much lower then the one we calculated and there are some good reasons for that

- Even though the gain should increase as an ideal current source has infinite output impedance in practicality less so, and thus due to this reason the gain is lower

- If we notice this gain is lower than RSS case as well, this may have happened due to decrease in Common Mode Rejection Ratio which directly affects differential gain.

- We have not yet accounted for the channel length modulation which can actually substantially decrease the gain

## AC ANALYSIS

![Screenshot 2025-03-14 195504](https://github.com/user-attachments/assets/91c0c449-fda6-424d-b6fa-ad6669ac88ac)

dB gain (Theoretical) = 20 log(AV) = 6.24 dB
dB gain (From graph) = 6.1107 dB (close to theoretical value)
-3dB gain = 35.80 GHz
Bandwidth = 35.80 GHz

Now we can move to our final case

## CASE 3 : With NMOS

Circuit Setup

![Screenshot 2025-03-14 192743](https://github.com/user-attachments/assets/57040906-692c-4d89-9a70-8a4a6700b622)

![Screenshot 2025-03-13 231937](https://github.com/user-attachments/assets/75955f64-0e16-4cc1-a663-1e9510318726)

We have set the W value for the nmos3 by keeping the L to be 189nm.

## DC ANALYSIS

![Screenshot 2025-03-13 232203](https://github.com/user-attachments/assets/5948dea6-1958-41c8-92ed-cb6efebc6bb1)

For better understanding

![Screenshot 2025-03-13 232245](https://github.com/user-attachments/assets/681c2402-22b7-486e-b167-2a1ca0f3444c)

## TRANSIENT ANALYSIS

![Screenshot 2025-03-13 232628](https://github.com/user-attachments/assets/58e2adf4-cd71-4745-846f-dbdc3d78095b)

The gain is -2.51V/V. 180 degree phase shift.

## AC ANALYSIS

![Screenshot 2025-03-13 232912](https://github.com/user-attachments/assets/eaf97da0-f1cb-4d1f-8c9d-7298c5ec8bfa)

- dB gain (Theoretical) = 20 log(AV) = 7.9934 dB
- dB gain (From graph) = 8.127 dB (close to theoretical value)
- -3dB gain = 28.58 GHz
- Bandwidth = 28.58 GHz

INFERENCE

- Mosfet based differential circuit is highly preferable to use in ICs since it has high CMRR, draws minimal power, high gain, high input impedance.
-  We calculate some value for input and output swing but distortions and clipping starts with much smaller signals this can be attributed to various factors including channel width modulation and other factors
-   We calculate some value for input and output swing but distortions and clipping starts with much smaller signals this can be attributed to various factors including channel width modulation and other factors
-   The gain in the differential is determine by the resistor value in the circuite
- Body effect various by thershold voltage
- 
