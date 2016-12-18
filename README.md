# Sigma-Delta-ADC-Modulator-Simulator
Python Tkinter based visual simulation of a first-order Sigma-Delta Modulator used in Sigma-Delta ADCs.

## Overview
Basic illustration of the working principle of a Sigma-Delta Modulator.
Displays the values generated by each of the components: the analogue adder/subtractor, the integrator, the comparator and the 1-bit DAC.

##Working principle
The input voltage (Vin) and the reference voltage for the DAC (Vref) must be entered by the user. "Simulation step" is used to set the speed of the simulation.
At reset all outputs are 0.
The DAC output (0 at reset) is subtracted from the input voltage using the analogue adder/subtracted.
The integrator adds the result from the summing node to a value stored from the previous integration step (0 at reset).
The comparator outputs logic 1 if the output of the integrator is greater than or equal to 0 or logic 0 otherwise.
The 1-bit DAC outputs +Vref if the comparator output is 1 or -Vref is the comparator output is 0.

The "Current generated value" is computed based on the number of 0s and 1s from the comparator output only if there is a repeating sequence. The larger the repeating sequence, the more accurate the generated value.
For example if Vin = 1V and Vref = 2.5V and the repeating sequence is "1011" (4 bits) the generated value is ADCout = 1.25

<img src="https://latex.codecogs.com/gif.latex?ADCout&space;=&space;\frac{N1}{Nb}&space;\cdot&space;2\cdot&space;Vref&space;-&space;Vref" title="ADCout = \frac{N1}{Nb} \cdot 2\cdot Vref - Vref" />

where N1 = number of 1s; Nb = number of bits

![Screenshot1](/../screenshots/adc1.JPG?raw=true "")

If the repeating sequence is "1011101101" then ADCout = 1 = Vin.

![Screenshot2](/../screenshots/adc2.JPG?raw=true "")
