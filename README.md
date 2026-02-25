## Ranjan_T_4NI24EC121
# EXPERIMENT-1: Design CS amplifier using nmosfet in tsmc 180nm in LTspice software

### Q1) Design a common source amplifier using NMOS transistor in TSMC 180nm technology library using LTspice with the given initial conditions:
###   suply voltage (VDD) = 1.5v
###   power constraint p \(\le \) 
###   load capacitance CL = 1pF
###   chanel length Ln = 180nm
## Introduction
### Amplifiers are fundamental elements in analog integrated circuits that are used to strengthen weak electrical signals. Among the MOSFET amplifier configurations —
### Common Source (CS), 
### Common Drain (CD), and
### Common Gate (CG) 
### the Common Source amplifier is most commonly used for voltage amplification due to its ability to provide substantial gain.
### The Common Source configuration offers:
### High voltage gain
### Moderate input impedance
###  Relatively good output impedance
### 180° phase inversion between input and output
### In comparison:
### Common Drain → acts mainly as a unity-gain buffer
### Common Gate → suitable for current amplification and high-frequency operation
### Because of these characteristics, the CS amplifier is widely employed in general analog voltage amplification stages.
### A MOSFET behaves as a voltage-controlled current device. Small variations in gate-to-source voltage control the drain current, which produces a voltage drop across the drain resistor and results in an amplified output ### signal. For proper amplification, the transistor must operate in the saturation region:
�
�
### In integrated MOS transistors, unavoidable internal capacitances exist between terminals, namely:
### Gate–Source capacitance (Cgs)
### Gate–Drain capacitance (Cgd)
### Drain–Body capacitance (Cdb)
### These parasitic capacitances influence the high-frequency performance of the amplifier and reduce gain at higher frequencies.
### When an external load capacitance is connected at the output node:
### Bandwidth decreases
### Gain-bandwidth trade-off becomes evident
### Thus, the effect of load capacitance on amplifier gain and frequency response is an important aspect in CS amplifier design.
## Device Parameters
### Technology used: TSMC 180 nm CMOS
### Supply voltage VDD = 1.5 V
### Maximum power dissipation P ≤ 0.5 mW
### Load capacitance CL = 1 pF
### Channel length Ln = 180 nm
### Chosen design values:
### Drain current ID ≈ 0.3 mA
### Drain resistor RD ≈ 2.4 kΩ
### NMOS width W ≈ 14 µm
### Aspect ratio �
### Drain voltage (bias) ≈ 0.75 V
### These parameters ensure that the MOSFET operates in saturation region while satisfying the given power constraint and allowing symmetrical signal swing.
