## Ranjan_T_4NI24EC121
# EXPERIMENT-1: Design CS amplifier using nmosfet in tsmc 180nm in LTspice software

#### Q1) Design a common source amplifier using NMOS transistor in TSMC 180nm technology library using LTspice with the given initial conditions:
####   suply voltage (VDD) = 1.5v
####   power constraint p \(\le \) 
####   load capacitance CL = 1pF
####   chanel length Ln = 180nm
## Introduction
#### Amplifiers are fundamental elements in analog integrated circuits that are used to strengthen weak electrical signals. Among the MOSFET amplifier configurations —
#### Common Source (CS), 
#### Common Drain (CD), and
#### Common Gate (CG) 
#### the Common Source amplifier is most commonly used for voltage amplification due to its ability to provide substantial gain.
#### The Common Source configuration offers:
#### High voltage gain
#### Moderate input impedance
####  Relatively good output impedance
#### 180° phase inversion between input and output
#### In comparison:
#### Common Drain → acts mainly as a unity-gain buffer
#### Common Gate → suitable for current amplification and high-frequency operation
#### Because of these characteristics, the CS amplifier is widely employed in general analog voltage amplification stages.
#### A MOSFET behaves as a voltage-controlled current device. Small variations in gate-to-source voltage control the drain current, which produces a voltage drop across the drain resistor and results in an amplified output ### signal. For proper amplification, the transistor must operate in the saturation region:
�
�
#### In integrated MOS transistors, unavoidable internal capacitances exist between terminals, namely:
#### Gate–Source capacitance (Cgs)
#### Gate–Drain capacitance (Cgd)
#### Drain–Body capacitance (Cdb)
#### These parasitic capacitances influence the high-frequency performance of the amplifier and reduce gain at higher frequencies.
#### When an external load capacitance is connected at the output node:
#### Bandwidth decreases
#### Gain-bandwidth trade-off becomes evident
#### Thus, the effect of load capacitance on amplifier gain and frequency response is an important aspect in CS amplifier design.
## Device Parameters
#### Technology used: TSMC 180 nm CMOS
#### Supply voltage VDD = 1.5 V
#### Maximum power dissipation P ≤ 0.5 mW
#### Load capacitance CL = 1 pF
#### Channel length Ln = 180 nm
#### Chosen design values:
#### Drain current ID ≈ 0.3 mA
#### Drain resistor RD ≈ 2.4 kΩ
#### NMOS width W ≈ 14 µm
#### Aspect ratio �
#### Drain voltage (bias) ≈ 0.75 V
#### These parameters ensure that the MOSFET operates in saturation region while satisfying the given power constraint and allowing symmetrical signal swing.
## circuit
<img width="487" height="378" alt="image" src="https://github.com/user-attachments/assets/d78145a6-3aa2-46b7-aef6-a1b5303c1f80" />

## DC Analysis
#### power given 
#### P ≤ 0.5
#### since:
#### p ≤ VDD*ID
#### P/VDD
#### ID ≤ P/VDD
#### ID ≤ (0.5×10^-3)
#### ID ≤ 333.333
#### let us assume
#### ID = 200uA
#### power
#### P ≤ ID * VDD
#### 200uA*1.5
#### 0.3 
#### current can be taken less than 333.333uA
### Mid point Bias
#### Midpoint Bias
#### In a Common Source amplifier, proper biasing of the MOSFET is necessary to allow the output voltage to vary over the #### widest possible range without distortion. If the transistor is biased too close to cutoff or saturation, one side of #### output waveform will be clipped, resulting in nonlinear amplification.
#### To avoid this, the operating point (Q-point) is selected near the center of the DC load line. When the drain voltage is #### approximately half of the supply voltage, the output can swing equally in both positive and negative directions. This #### condition ensures maximum symmetrical signal excursion and minimizes distortion.
#### Therefore, for midpoint bias in a CS amplifier, the drain voltage is usually chosen as:
#### VD = VDD/2
#### This biasing approach provides optimal dynamic range and stable amplifier operation.
#### Drain resistor:
#### RD = (VDD-VDS)/ID
#### RD = (1.5-0.75)/200uA
### For saturation region:
#### VDS ≥ VGS -VTH 
#### 0.75 ≥ VGS - 0.38
#### VGS ≥ 1.11 V
#### by mosfet ID Eqn
#### ID = (1/2)/un Cox(W/L)(VGS - VTH)^2
#### W = (2ID L)/(uN Cox(VGS - Vth)^2)
#### we get w =1.07
#### theoritically for ID = 200uA we get w=1.07um
#### practically for ID = 200um we gwt w=1.534um
#### therefore from current Eqn ID is directly proportional to w and 
#### length is inversely proportional
