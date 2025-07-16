# Voltage Controlled Oscillator(VCO) Project

# What is Voltage Controlled Oscillator(VCO)

* A voltage-controlled oscillator is an oscillator whose output can be varied over a range, which is controlled by the input DC voltage. It is an oscillator whose output frequency is directly related to the voltage at its input.
* The oscillation frequency varies from a few hertz to hundreds of GHz. By varying the input DC voltage, the output frequency of the signal produced is adjusted.

# Voltage Controlled Oscillator Applications

* (a) Function generator by square and triangular wave generator
* (b) Music Synthesizers generate audio signals that can be manipulated to create various sounds and effects
* (c) Phase locked loop (PLL) main component in this system
* (d) Frequency synthesizers or generators/analyzers, to generate stable output frequencies that are integer multiples of a reference frequency
* (e) Frequency Modulation (FM) Radio Transmitters and Receivers use for carrier frequency
* (f) Electronic jamming equipment by generating a continuous wave or modulated signal at the same frequency as the target system's operating frequency
* (g) Clock Generation in microprocessor,FPGA, DSP application
* (h) Radar Systems by generate the necessary frequencies for transmitting radar pulses and processing the returned echoes
* (i) GPS Receivers helps in generating the high-precision frequencies required to lock onto satellite signals and determine position
* (j) Television by generating the carrier signal for tuning into different channels

# Working Principle of VCO

* Consider the unity-gain negative-feedback Vout/Vin(s) = H(s)/[1 + H(s)]
* If a negative-feedback circuit has a loop gain that satisfies two conditions:
|H(jω0)| ≥ 1
H(jω0) = 180degree
* That is Barkhausen’s Criteria, in RC and LC based VCO Circuits the frequency is given by f=1/2piRC and f= 1/2pirt(LC) respectively so as the C value decreases the output f increase by inversely proportionate and as it follows Linear relation with voltage, hence also so as input voltage increase the output frequency increases, same follows for other case.The control voltage and frequency of oscillations are directly proportional. That is, when one increases, the other will increase.
* We can see that at nominal control voltage represented by Vc(nom), the oscillator works at its free running or normal frequency, fc(nom).
* As the control voltage decreases from nominal voltage, the frequency also decreases and as the nominal control voltage increases, the frequency also increases.

# Characteristic of VCO

![image](https://github.com/user-attachments/assets/c23a527d-8e39-4d1d-bbf3-1a579b1d8a82)

# Performance Parameter

* Center Frequency: The center frequency is determined by the environment in which the VCO is used. For example, in the clock generation network of a microprocessor,the VCO may be required to run at the clock rate or even twice that. Today’s CMOS VCOs achieve center frequencies as high as hundreds of gigahertz.
  
* Tuning Range: The required tuning range is dictated by two parameters: (1) the variation of the VCO center frequency with process and temperature, and (2) the frequency range necessary for the application.The center frequency of some CMOS oscillators may vary by a factor of two at the extremes of process and temperature, thus mandating a sufficiently wide (≥ 2×) tuning range to guarantee that the VCO output frequency can be driven to the desired value. Also, some applications incorporate clock frequencies that must vary by one to two orders of magnitude depending on the mode of operation, demanding a proportionally wide tuning range. An important concern in the design of VCOs is the disturbance of the output phase and frequency as a result of noise on the control line. For a given noise amplitude, the noise in the output frequency is proportional to KVCO because ωout = ω0 + KVCO Vcont
  
* Tuning Linearity: Actual oscillator characteristics typically exhibit a high-gain region in the middle of the range and a low gain at the two extremes. Compared to a linear characteristic (the gray line), the actual behaviour displays a maximum gain greater than that predicted by implying that, for a given tuning range, nonlinearity inevitably leads to higher sensitivity for some region of the characteristic.
  
* Output Amplitude : It is desirable to achieve a large output oscillation amplitude, thus making the waveform less sensitive to noise. The amplitude trades with power dissipation, supply voltage, and even the tuning range. Also, the amplitude may vary across the tuning range,an undesirable effect.
  
* Power Dissipation: As with other analog circuits, oscillators suffer from trade- offs among speed, power dissipation, and noise. Typical oscillators drain 1 to 10 mw of power.
  
* Output Signal Purity: Even with a constant control voltage, the output waveform of a VCO is not perfectly periodic. The electronic noise of the devices in the oscillator and supply noise lead to noise in the output phase and frequency. These effects are quantified by “jitter” and “phase noise” and determined by the requirements of each application

# Key Specification

* Phase Noise(P.N.): The short-term frequency fluctuations of an oscillator, typically measured in dBc/Hz at a specified offset from the carrier frequency.
* Supply Voltage: The required voltage to Turn ON the VCO is Vdd
* Control Voltage: The range of input voltages over which the VCO can be tuned is Vctrl
* Output/Oscillation Frequency(fo): fo is the actual frequency output by the VCO, which varies with the control voltage applied to the oscillator
* Center/Carrier Frequency(fc): This is the main or center frequency around which the VCO operates. It is the nominal frequency output by the VCO when the control voltage is at a reference level
* Power Consumption(PDC): The amount of power the VCO consumes during operation, usually measured in milliwatts (mW)
* Frequency Tuning Range(FTR): The range of frequencies over which a VCO can operate.  "FTR(%)= (fmax-fmin)*100/fo"
* Figure of Merit(FOM): FOM provides a standardised way to assess the efficiency of a VCO by normalising phase noise performance with respect to offset frequency and power consumption
![image](https://github.com/user-attachments/assets/0f38e7ee-f100-414c-8f25-837b4af49a55)
* VCO Gain or VCO Sensitivity(Kvco): It indicates how much the output frequency of the VCO changes in response to a change in the control voltage
Kvco =Δfout /ΔVcontrol
* Offset Frequency(Δf): Its the frequency difference from the carrier frequency at which specific characteristics of VCO, like phase noise, are measured
  
# Types of VCO

![image](https://github.com/user-attachments/assets/ef7973ca-9e15-4db0-afa2-753c1ac81215)

# Three Stage Ring Oscillator

![image](https://github.com/user-attachments/assets/fa04396e-9489-48bc-86a9-e8f648205788)

* As two and single stage doesn't satisfy Barkhausen Criteria so we have shown three stage Ring Oscillator:

![image](https://github.com/user-attachments/assets/082c0536-66eb-4597-93de-8911a4d1ab0b)

![image](https://github.com/user-attachments/assets/b7072598-0205-4428-b9e2-505a32af5b6a)

* In summary, a three-stage ring oscillator requires a low-frequency gain of 2 per stage, and it oscillates at a frequency of √3 ω0, where ω0 is the 3-dB bandwidth of each
stage
* Since each stage contributes a frequency-dependent phase shift of 60◦ as well as a low-frequency signal inversion, the waveform at each node is 240◦ (or 120◦) out of
phase with respect to its neighbouring nodes
* The ability to generate multiple phases is a very useful property of ring oscillators
* Suppose the circuit is released with an initial voltage at each node equal to the trip point of the inverters,Vtrip (The trip point of an inverter is the input voltage that
results in an equal output voltage)
* With identical stages and no noise in the devices, the circuit would remain in this state indefinitely, but noise components disturb each node voltage, yielding a
growing waveform. The signal eventually exhibits rail-to-rail swings.

![image](https://github.com/user-attachments/assets/2563b114-7b3a-43a1-9f63-6ebc69860318)

![image](https://github.com/user-attachments/assets/46d43774-93bc-4832-965c-9d727f2b549c)

* Lets begins with VX = VDD . Under this condition, VY = 0 and VZ = VDD. Thus, when the circuit is released, VX begins to fall to zero (because the first inverter senses a
high input), forcing VY to rise to VDD after one inverter delay, TD, and VZ to fall to zero after another inverter delay. The circuit therefore oscillates with a delay of TD between consecutive node voltages, yielding a period of 6TD
* While the small-signal oscillation frequency is given by A0√3ω0/2 when the circuit is released with all inverters at their trip point, the oscillation begins
with a frequency of √3A0ω0/2, but, as the amplitude grows and the circuit becomes nonlinear, the frequency shifts to 1/(6TD) (which is a lower value)

# Differential Ring VCO

![image](https://github.com/user-attachments/assets/78c41502-bf5c-4a60-9ede-ffba9656b97c)

* Here, M5 operates in the deep triode region and amplifier A1 applies negative feedback to the gate of M5. If the loop gain is sufficiently large, the differential input
voltage of A1 must be small, giving VP ≈ VREF and |VDS5| ≈ VDD − VREF .
* Thus, the feedback ensures a relatively constant drain-source voltage even if I1 varies. In fact, as I1, say, decreases, A1 raises the gate voltage of M5 such that Ron5
I1 ≈ VDD − VREF
* The idea is to “serve” the on-resistance of M3 and M4 to that of M5 and vary the frequency by adjusting I1 and ISS simultaneously. If M3 and M4 are identical to M5 and ISS to I1, then VX and VY vary from VDD to VDD-VREF as M1 and M2 steer the tail current to one side or the other. 
* Thus, if process and temperature variations, say, decrease I1 and ISS, then A1 increases the on-resistance of M3–M5, forcing VP and hence VX and VY (when M1 or M2 is fully on) equal to VREF The bandwidth of the op amp A1 in Figure is of some concern.
* If a change in Vcont takes a long time to change ωout, then the settling speed of a PLL using this VCO degrades significantly.

# Current Straved VCO

![image](https://github.com/user-attachments/assets/ceb73701-fb34-47db-8478-db25d19b81d4)

* The current starved ring VCO illustrates a wide oscillation frequency range of 66–875 MHz at 1.8 V supply voltage using 180nm CMOS technology.
* The circuit formed by using a ring oscillator consists of odd number of gain stages connected in series and bias stage consists of current sink and current source. The oscillation is performed by ring oscillator, and the frequency tuning is achieved by controlling the supply current.
* The variable bias currents are used to control the oscillation frequency of this ring VCO.
* The transistors M1 and M2 operate as inverters while M3 and M4 operate as current sink and current source, respectively. The current sources limit the current available to inverters. The drain currents of transistors M5 and M6 are the same and are set by the input control voltage Vctrl. The current in transistors M4 and M5 is mirrored from bias stage to each cascaded inverting stage. The bias circuit is used to provide correct polarisation for transistors M3 and M4.
* The tuning of frequency of oscillation for a wide range can be done by changing the value of control voltage and this is the benefit of this configuration. The linearity and bandwidth of VCO are determined by variation of control voltage Vctrl.
* The main drawback of this circuit is that under low frequency, the current-starved inverter suffers from slow rise and fall at its output. Frequency of oscillation is given by fosc = Id/2NCtotalVctrl

# Inductor Capacitor VCO (LC-VCO)

* The oscillation frequency of LC topologies is equal to fosc = 1/(2π√LC), suggesting that only the inductor and capacitor values can be varied to tune the frequency, and other parameters such as bias currents and transistor transconductances affect fosc negligibly. Since it is difficult to vary the value of monolithic inductors, we simply change the tank capacitance to tune the oscillator.
* Voltage-dependent capacitors are called “varactors.” A reverse-biased pn junction can serve as a varactor.
<img width="958" height="368" alt="image" src="https://github.com/user-attachments/assets/c33b68ee-5c42-4fdc-9779-9aeceb95632a" />

* To avoid forward-biasing D1 and D2 significantly, Vcont must not exceed VX or VY by more than a few hundred millivolts. Thus,if the peak amplitude at each node is A, then 0 < Vcont < VDD − A + 300 mV, where it is assumed that a forward bias of 300 mV creates negligible current.
* Interestingly, the circuit suffers from a trade-off between the output swing and the tuning range. This effect appears in most LC oscillators.
* Note that, since the swings at X and Y are typically large (e.g., 1 Vpp at each node), the capacitanceof D1 and D2 varies with time. Nonetheless, the “average” value of the Capacitance is still a function of Vcont , providing the tuning range.
* So, the varactor diode is represented by Simple diode with series resistance of diode and a capacitance Cn represents the (voltage-dependent) capacitance between the n-well and the substrate.
<img width="216" height="157" alt="image" src="https://github.com/user-attachments/assets/e39cbc68-8c3f-4c57-9b17-c84b96405d8f" />


![image](https://github.com/user-attachments/assets/1affed8a-2e95-40cc-8294-d6f3f425246f)

* An inductor L1 placed in parallel with a capacitor C1 resonates at a frequency ωres = 1/√L1C1. At this frequency, the impedances of the inductor, j L1ωres, and the capacitor, 1/(jC1ωres), are equal and opposite, thereby yielding an infinite impedance.
* So, the circuit has an infinite quality factor, Q In practice, inductors (and capacitors) suffer from resistive components. For example, the series resistance of the metal wire used in the inductor can be modelled as shown in the below figure . We define the Q of the inductor as L1ω/Rs.

## Paper 1: Comparative Study of Ring VCO and LC-VCO: Design, Performance Analysis, and Future Trends A Comparative Study of Ring VCO and LC-VCO: Design, Performance Analysis, and Future Trends( 8 November,2023 )

### Phase Noise Analysis of the all reported VCOs
* Phase noise can be expressed as the proportion of noise within a 1-Hz bandwidth at a given frequency offset (fm), relative to the amplitude of the oscillator signal at the
frequency (fo). A comparison between the phase noise of the ring VCO and the LC-VCO, as stated in the reported work. As a consequence of the literature survey, the phase noise of the Ring VCOs varied between −86.13 dBc/Hz and −110 dBc/Hz, and for the LC-VCO is between −110.5 to −136.57 dBc/Hz. Therefore, it is concluded that to have a better phase noise, LC-VCO would be a better option as compared to Ring-based VCO circuits.
* The comparison between the phase noises reported by Class-B to Class-F and Colpitts oscillators in harmony with the reported work and the results. Therefore, researchers summarise the evidence that the colpitts oscillator brings superior PN upto −140 dBc/Hz, class-C and Class-D: similarly Class- C up to -135 and others can provide moderate phase noise.

### Operating Frequency analysis of the reported VCOs:

* A VCO’s maximum operational frequency is the highest frequency, which it can consistently and accurately produce an output signal.It demonstrates the maximum
operating frequency ranges of ring-based VCO, The maximum operating frequency ranges of LC-based VCO, the comparison between the maximum operating frequency ranges of Ring- based VCO as well as LC- based VCO and the maximum operating frequency ranges of Class-B to class-F LC- VCO and Colpitts LC-VCO respectively.
* Consequently, it is identified from the literature survey that the ring-based VCO can opt for radio frequency ranges from 0.4 GHz to 4.3 GHz. Similarly, the LC-VCO can be selected for both radio frequency as well as millimeter wave range frequencies, ranging from 1.5 GHz to 105.2 GHz.

## FOMs analysis of all reported VCOs:

* With a greater negative value or a larger absolute value of the FOM, the performance of the VCO is better. According to the FOM observations of the VCOs, the LC-VCO can deliver better phase noise and a higher operating frequency when compared to the ring VCO, which is adequate for high-frequency mm-wave range applications.

### Conclusion from Paper-1:

* The comparison between the Ring and LC-VCOs architectures. Furthermore, both VCO designs propose unique advantages and trade-offs, making them suitable for different applications.
* Moreover, the Ring VCO has the advantage of a simpler design in its circuit implementation, and it is suitable for low-power and low-frequency applications. Therefore, the LC-VCO imparts an extraordinary phase noise performance and higher output frequency at the cost of a low tuning range.
* Also, LC-VCO generally requires more complex circuitry and may suffer FOM large chip area and fabrication costs also high. According to the study, using an LC-VCO, one could acquire a millimeter wave range frequency.
* Therefore, future research directions may concentrate on implementing high-tuning range LC-VCOs for reducing the complexity of the circuits, area, and power consumption.
* Also, in NMOS based LC-VCO is on the winning side for operating at High Frequency, Lower Phase Margin and Highest Negative FOMs

# Paper-2: Small Signal Analysis of NMOS Cross-Coupled LC-VCO:

![image](https://github.com/user-attachments/assets/53c43be8-6657-451f-9318-3ca2af439d2e)

![image](https://github.com/user-attachments/assets/74cf2fac-e836-43e0-8f30-2512d26c7365)

![image](https://github.com/user-attachments/assets/9f79c1f2-cf94-473d-800f-dcd1aabf3121)

# Working of Cross-Coupled LC VCO:

* Initial Noise: A small noise signal starts the oscillation in the LC tank circuit.
* Amplification: The noise signal is amplified by the cross-coupled transistors.
* Feedback Loop: The amplified signal is fed back into the LC tank, reinforcing the oscillations.
* Negative Resistance: The transistors provide negative resistance to counteract losses and sustain oscillations.
* Tuning: Varactors adjust the capacitance in the LC tank, changing the oscillation frequency.

# Simulation of LC VCO:
### Design of 6.7 GHz~7.518 GHz Cross-Coupled LC-VCO in 180nm CMOS technology by Sophiya Susan S and Dr. Siva S Yellampalli 

* We are simulating using gpdk 45nm CMOS technology is good choice since it reduces cost and has low power compared to other technologies. 
* The most widely used oscillator structures are Ring oscillators and LC oscillators. Considering that the Phase noise parameter is better for an LC oscillator compared to the poor phase noise of a ring oscillator, in this paper, we chose an LC oscillator for implementation.
* The topology of PMOS only circuit has similarity with the NMOS only topology. However,with the variations in the mobility, the size of transistors is twice greater than nmos transistor to achieve the similar transconductance. Hence PMOS cross coupled VCO consume more power when compared to other two topologies. 
* Compared to PMOS cross coupled VCO, NMOS cross coupled VCO consumes less power and low phase noise
* Advantages of CMOS cross-coupled VCOs compared to other two are, CMOS cross coupled VCOs gives double the output amplitude compared to the NMOS cross-coupled circuit, power consumed is less,low Phase noise and higher transconductance
* Before actually implementing the entire CMOS cross coupled LC VCO, analyzing the ac and transient behavior of the basic parallel resonator circuit is important.

# AC Analysis of Parallel Resonator Circuit:
![Screenshot from 2025-05-06 11-29-12](https://github.com/user-attachments/assets/1a8d3d81-1388-4f0f-a644-9aacd5259450)

# Reference

* (i) Design of Analog CMOS Integrated Circuits, Second Edition- By Behzad Razavi
* (ii) A Comparative Study of Ring VCO and LC-VCO: Design, Performance Analysis, and Future Trends- by - N. R. SIVARAAJ AND K. K. ABDUL MAJEED( 20 November,2023,IEEE Access)
* (iii) Design of 6.7 GHz ~7. 518 GHz Cross Coupled LC-VCO in 180nm CMOS technology- by- Sophiya Susan S, Dr. Siva S Yellampalli (Fifth International Conference on Computing Methodologies and Communication (ICCMC 2021))
* (iv) A Voltage Controlled Oscillator with Inductive Divider Design and Analysis at Frequencies Above 100 GHz -by- Yasir Shafiullah,Rehman Akbar, Mikko Hietanen, Aarno Pärssinen from University of Oulu, Oulu, Finland  
* (v) An Ultra-Low Phase Noise Low-Power 10-GHz LC-VCO with High-Q Common- Mode Harmonic Resonance for 5G Systems-by -Yahia Ehab, Ahmed Naguib, and Hesham N. Ahmed (2023 International Microwave and Antenna Symposium(IMAS))

# Acknowledgement

* I am grateful and thankful to Dr.Sakshi Arora(Analog Professor) for mentoring and helping me to complete this Summer Project with valuable learning successfully.

