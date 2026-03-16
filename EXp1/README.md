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
## DC operating point 
<img width="456" height="221" alt="image" src="https://github.com/user-attachments/assets/c9aa3f92-c007-48d2-a08b-1eb91a15c95f" />

#### since VDS = 0.75 
#### ie.. VGS ≥ Vth
#### VDS ≥ VGS - Vth 
#### mosfet is in saturation region
## DC Sweep Analysis
#### DC Sweep analysis in LTspice is a simulation in which the DC value of a selected voltage or current source is varied #### step by step within a defined range. At each step, the simulator determines the corresponding DC operating point of the #### circuit.
#### In MOSFET-based circuits, sweeping the gate-to-source voltage � is useful for:
#### Determining the threshold voltage of the transistor
#### Studying the variation of drain current � with �
#### Identifying cutoff, triode, and saturation regions
#### Selecting an appropriate bias point (Q-point) for amplifier operation
<img width="1600" height="745" alt="image" src="https://github.com/user-attachments/assets/5e17b5c0-c42a-4982-ba51-d8ef6cae353e" />

## Transient Analysis
### (Time-Domain Response)
#### A sinusoidal input signal of 1 kHz was applied at the gate terminal of the MOSFET to examine the time-domain behavior #### of the Common Source amplifier. Transient simulation is used to confirm voltage amplification, phase reversal, and #### #### linear response of the amplifier around its bias point.
#### Input Signal (Vin)
#### Frequency : 1 kHz
#### Amplitude : 19.192 mV peak-to-peak
#### The applied signal amplitude is kept sufficiently small so that the MOSFET remains in the small-signal operating region #### about the chosen Q-point.
<img width="1600" height="758" alt="image" src="https://github.com/user-attachments/assets/b32f522a-1d1e-4f3f-8e99-b80f6e80f18b" />

### output Signal (Vout)
#### Measured amplitude : 43.919 mV peak
#### The output waveform obtained from transient simulation shows an amplified sinusoidal signal at the drain terminal. The #### output is inverted with respect to the input, confirming the 180° phase shift characteristic of the Common Source #### #### amplifier. The observed amplitude indicates proper voltage amplification while maintaining linear operation around the #### bias point.
<img width="1600" height="756" alt="image" src="https://github.com/user-attachments/assets/121302ca-dd70-4457-a8b1-50a10196dc8a" />


###Input and Output Signals
#### Input (Vin)
#### Frequency : 1 kHz
## Amplitude : 19.192 mV peak-to-peak
#### Output (Vout)
#### Measured amplitude : 43.919 mV peak
#### A small sinusoidal signal was applied at the gate of the MOSFET, and the corresponding output was observed at the drain #### terminal. The output waveform is amplified and exhibits a 180° phase reversal relative to the input, confirming the #### characteristic behavior of a Common Source amplifier. The measured output amplitude demonstrates that the amplifier #### provides voltage gain while operating in the linear region around the selected bias point.
<img width="1600" height="745" alt="image" src="https://github.com/user-attachments/assets/c3b01e4a-d89a-4aeb-8d5e-74b34a03fcc7" />

#### Gain Av = 2.775 v/v
#### in dB = 8.865 dB


## AC Analysis
### Without Load Capacitor
#### When no external load capacitance is connected at the output, the frequency response of the Common Source amplifier is #### mainly determined by the intrinsic parasitic capacitances of the MOSFET. Due to the absence of additional capacitive #### loading, the amplifier exhibits a wide bandwidth and maintains nearly constant gain over the mid-frequency region. The #### gain starts decreasing only at very high frequencies where the internal device capacitances become dominant.
#### 3 dB Gain : ≈ 4.189 dB
#### Upper Cutoff Frequency : ≈ 100 GHz
<img width="1600" height="770" alt="image" src="https://github.com/user-attachments/assets/4174e560-f124-461c-9c5d-c8222e04205b" />

<img width="455" height="347" alt="image" src="https://github.com/user-attachments/assets/932a9772-4864-4332-9b7c-a524601f30a5" />

<img width="959" height="457" alt="image" src="https://github.com/user-attachments/assets/845f8ffe-d7b8-4275-8038-32c4c655d1b9" />

