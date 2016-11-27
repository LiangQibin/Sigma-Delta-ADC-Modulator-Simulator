# Sigma-Delta-ADC-Modulator-Simulator
Python Tkinter based visual simulation of a first-order Sigma-Delta Modulator used in Sigma-Delta ADCs.

## Overview
Basic illustration of the working principle of a Sigma-Delta Modulator.
Displays the values generated by each of the components: the analogue adder/substracter, the integrator, the comparator and the 1-bit DAC.

##Working principle
The input voltage (Vin) and the reference voltage for the DAC (Vref) must be entered by the user.
At reset all outputs are 0.
###1st step
The DAC output (0 at reset) is substracted from the input voltage using the analogue adder/substracter.

###2nd step
The integrator adds the result from the summing node to a value stored from the previous integration step (0 at reset).

###3rd step
The comparator outputs logic 1 if the output of the integrator is greater than or equal to 0 or logic 0 otherwise.

###4th step
The 1-bit DAC outputs +Vref if the comparator output is 1 or -Vref is the comparator output is 0.

The "Current generated value" is computed based on the number of 0s and 1s from the comparator output only if there is a repeating sequence. The larger the repeating sequence, the more accurate the generated value.
For example if the repeating sequence "11"

[Petersen Graph][reference-id-for-petersen-graph]
[reference-id-for-petersen-graph]:http://google.ro
