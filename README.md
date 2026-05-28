# Drone-charging-WPT-Sims
Simulation for IP 
1. Given a dc voltage generate a sinusoidal signal (Mhz) of peak 12-15V and transmit it to receiver coil via coupling then output that
   received time varying voltage VSin(wt) to rectifier and convert it to a DC voltage and test with arduino
   Output requirements :
    First Phase: For powering arduino 
    Design Target is 5V, 500mA
    
    Second Phase: For WPT charger for 3S Battery:
    Rectifier DC output	14–15 V
    Regulated charger output	12.6 V
    Charging current	1–2 A
    Output power	20–30 W

Week 1: 18th may - 25th may complete phase one atleast sim

new ClassE inverter is coupled with a coil and is showing good efficiency across R1 resistor above 90% with smooth sinusoidal voltage and current drawing around Pavg 5.3W where the voltage source provides a power of 5.8W currently the inverter Q is balanced at 3.01 (wL1/Rl) = 50/16.6 = 2 whereas Q2 of secondary side is at 8.32
With $Q = 10$ (High-Q): The circuit acts like a razor-sharp filter. It tunes into exactly $5\text{ MHz}$ and will reject almost everything else.The Trap: This makes circuit incredibly fragile. If receiver moves slightly, or component tolerances are off by just a few picoFarads, the circuit falls out of alignment. Zero Voltage Switching (ZVS) will instantly collapse, and the MOSFET will start overheating.With $Q = 3$ (Low-Q): The tuning window is wide and forgiving.The Win: Because it has a wider bandwidth, Class E inverter can handle slight shifts in the coupling coefficient ($k$) or structural component drift without instantly breaking its ZVS profile. This is exactly why we targeting $Q=3$ for wireless setup!

Currently two more challenges remain one with a gate driver circuit design as in simulation we are using a voltage source that generates a 50% duty
cycle square pulse but in implementation we would need a gate driver that can provide upto 2A current and draw back instantly in 0.2u seconds interval
and wont dissipate a lot of power another challenge is to use synchronous rectification on receiver side that can save power that is dropped across the schottky diodes

