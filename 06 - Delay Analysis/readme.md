## Delay Analysis

Delay analysis is a critical aspect of VLSI design, impacting the performance and reliability of the circuit. In this project, we focus on the following types of delays:

### Propagation Delay

Propagation delay (t<sub>pd</sub>) is the time taken for a signal to travel from the input to the output of the inverter. Specifically, it is measured from the point where the input signal reaches 50% of its final value to the point where the output signal reaches 50% of its final value.

### Rise Time and Fall Time

- **Rise Time (t<sub>r</sub>)**: The time taken for the output signal to rise from 10% to 90% of its final value.
- **Fall Time (t<sub>f</sub>)**: The time taken for the output signal to fall from 90% to 10% of its final value.

<img title="Delay Analysis" width = 500 alt="installed files" src="Images\delay.png">

## Delay Analysis of CMOS inverter under sky130

#### Load the test bench

First load the test bench for the CMOS inverter. [See here](../04%20-%20VTC%20Analysis)

<img title="Test bench for CMOS inverter" width = 500 alt="installed files" src="Images/Screenshot from 2024-07-13 09-57-12.png">

#### Simulate the testbench
Click on **Net List** then **Simulate** in the right side of the menue bar.

Use Following spice commands (Need to do transient analysis)
```sh
    pname=s1 only_toplevel=false value=".lib /usr/local/share/pdk/sky130A/libs.tech/ngspice/sky130.lib.spice tt
    .tran .02n 40n
    .save all
    .end" 
```
For V<sub>in</sub> use following script
```sh
    "PULSE(0 1.8 0 .1n .3n 10n 20.6n 10)"
```  

After the simulation completed, run the following command to plot $V_{o}$ vs $V_{in}$.

```sh
    plot vin vout
```






