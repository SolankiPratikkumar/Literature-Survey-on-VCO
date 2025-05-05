# Summer Project on VCO

# What is Voltage Controlled Oscillator(VCO): 

* A voltage-controlled oscillator is an oscillator whose output can be varied over a range, which is controlled by the input DC voltage. It is an oscillator whose output frequency is directly related to the voltage at its input.
* The oscillation frequency varies from a few hertz to hundreds of GHz. By varying the input DC voltage, the output frequency of the signal produced is adjusted.

# Voltage Controlled Oscillator Applications:

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

# Working Principle of VCO:

* Consider the unity-gain negative-feedback Vout/Vin(s) = H(s)/[1 + H(s)]
* If a negative-feedback circuit has a loop gain that satisfies two conditions:
|H(jω0)| ≥ 1
H(jω0) = 180degree
* That is Barkhausen’s Criteria, in RC and LC based VCO Circuits the frequency is given by f=1/2piRC and f= 1/2pirt(LC) respectively so as the C value decreases the output f increase by inversely proportionate and as it follows Linear relation with voltage, hence also so as input voltage increase the output frequency increases, same follows for other case.The control voltage and frequency of oscillations are directly proportional. That is, when one increases, the other will increase.
* We can see that at nominal control voltage represented by Vc(nom), the oscillator works at its free running or normal frequency, fc(nom).
* As the control voltage decreases from nominal voltage, the frequency also decreases and as the nominal control voltage increases, the frequency also increases.

# Characteristic of VCO:

![image](https://github.com/user-attachments/assets/c23a527d-8e39-4d1d-bbf3-1a579b1d8a82)

# Performance Parameter:

* Center Frequency: The center frequency is determined by the environment in which the VCO is used. For example, in the clock generation network of a microprocessor,the VCO may be required to run at the clock rate or even twice that. Today’s CMOS VCOs achieve center frequencies as high as hundreds of gigahertz.
  
* Tuning Range: The required tuning range is dictated by two parameters: (1) the variation of the VCO center frequency with process and temperature, and (2) the frequency range necessary for the application.The center frequency of some CMOS oscillators may vary by a factor of two at the extremes of process and temperature, thus mandating a sufficiently wide (≥ 2×) tuning range to guarantee that the VCO output frequency can be driven to the desired value. Also, some applications incorporate clock frequencies that must vary by one to two orders of magnitude depending on the mode of operation, demanding a proportionally wide tuning range. An important concern in the design of VCOs is the disturbance of the output phase and frequency as a result of noise on the control line. For a given noise amplitude, the noise in the output frequency is proportional to KVCO because ωout = ω0 + KVCO Vcont
  
* Tuning Linearity: Actual oscillator characteristics typically exhibit a high-gain region in the middle of the range and a low gain at the two extremes. Compared to a linear characteristic (the gray line), the actual behaviour displays a maximum gain greater than that predicted by implying that, for a given tuning range, nonlinearity inevitably leads to higher sensitivity for some region of the characteristic.
  
* Output Amplitude : It is desirable to achieve a large output oscillation amplitude, thus making the waveform less sensitive to noise. The amplitude trades with power dissipation, supply voltage, and even the tuning range. Also, the amplitude may vary across the tuning range,an undesirable effect.
  
* Power Dissipation: As with other analog circuits, oscillators suffer from trade- offs among speed, power dissipation, and noise. Typical oscillators drain 1 to 10 mw of power.
  
* Output Signal Purity: Even with a constant control voltage, the output waveform of a VCO is not perfectly periodic. The electronic noise of the devices in the oscillator and supply noise lead to noise in the output phase and frequency. These effects are quantified by “jitter” and “phase noise” and determined by the requirements of each application

# Key Specification:

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
  
# Types of VCO:

![image](https://github.com/user-attachments/assets/ef7973ca-9e15-4db0-afa2-753c1ac81215)

# Three Stage Ring Oscillator:

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

# Differential Ring VCO:
* 

# Refer to the Above files after downloading them into your system, to access the complete report of Project
