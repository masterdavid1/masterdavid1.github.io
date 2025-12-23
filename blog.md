---
layout: article
titles: 'Blog Posts'
---

## 2025 May 19 — Capacitor Filtering vs Inductor Filtering

**Capacitor Filtering**  
The basic characteristic of a capacitor is to block direct current and pass alternating current. This is because the capacitive reactance of a capacitor is inversely proportional to the frequency of the alternating current, that is, Xc = 1 / (2πfC), meaning that the higher the frequency, the lower the capacitive reactance, and the lower the frequency, the higher the capacitive reactance.  
So it can be understood that capacitors are in a high-resistance state when it comes to direct current and extremely low-frequency alternating current, and thus cannot pass through. However, when it comes to high-frequency alternating current, a short-circuit effect occurs and it can pass through very easily.  
Capacitor filtering also takes advantage of this fundamental characteristic. For instance, the purpose of filter capacitors in power supplies is to filter out ripple, and the frequency of ripple is very low. When the frequency f is very small, to obtain a low capacitive reactance Xc, large-capacity capacitors need to be used. Therefore, filter capacitors are usually in the uf range, such as 10uF or 100uF polarized electrolytic capacitors.  
In addition to taking advantage of the impedance characteristics of capacitors to frequency, filter capacitors can also utilize the energy storage characteristics of capacitors, that is, the charging and discharging characteristics of capacitors, to filter out ripples and achieve the effect of voltage stabilization. For instance, in a rectifier circuit, if it is half-wave rectification, the alternating current will be rectified into periodic unidirectional pulsating direct current. The fluctuation of this ripple is too large, and the load cannot be used.

**Inductor Filtering**  
The basic characteristics of an inductor are exactly the opposite of those of a capacitor. An inductor "allows direct current and hinders alternating current". This is because the inductive reactance XL of an inductor is directly proportional to the frequency f and the inductance L, that is, XL=2πfL. That is to say, when the frequency of the signal is higher and the inductance value is larger, its inductive reactance is greater and its hindrance effect is stronger.  
The principle of inductance is Lenz's law. When the current flowing through an inductance coil changes, the induced electromotive force generated in the coil will hinder the change of the current, and the magnetic flux of the induced current always hinders the change of the magnetic flux that causes the induced current.  
So it can be understood that the inductor is in a high-resistance state at the moment of high-frequency alternating current, hindering its passage. When it is in direct current, it is equivalent to a wire and will have a short-circuit effect, making it very easy to pass through. Note that the high-resistance state here is merely an obstruction, not a stop. It can only delay the passage of the signal and allow it to pass through smoothly, rather than preventing it from passing.


## 2024 September 23 — Investor report review: Tesla's Dojo and the Future of Semiconductor Investment

**Introduction**  
In today's fast-changing technological environment, semiconductor investments are becoming increasingly popular. This essay provides an analysis and a synopsis of an investment report, concentrating on the significance of Tesla's Dojo and other significant semiconductor industry developments. Furthermore, unique perspectives and comments on the investor report will be offered.  
**Tesla's Dojo**  
A Game-Changer in Custom Chip Efficiency: As mentioned in the investor report, Tesla's Dojo is a game-changing development in custom chip efficiency. It seeks to outperform existing GPU systems such as NVIDIA's A100. According to Tesla and Morgan Stanley Research, Dojo has enormous potential benefits for the semiconductor sector (Morgan Stanley Research, 2024).  
**TSMC's Crucial Role**  
The report underlines TSMC's position as a critical enabler of Tesla's Dojo chip. Dojo's success depends on TSMC's sophisticated manufacturing methods and fast data transfer bandwidth. This collaboration emphasizes the significance of semiconductor foundries in enabling cutting-edge technology (Morgan Stanley Research, 2024).  
**AI ASICs vs. GP GPUs**  
The research looks into the battle between artificial intelligence ASICs and general-purpose GPUs. Custom AI ASICs will likely account for a significant market share, with energy efficiency and cost-effectiveness driving their adoption. According to the report, the upfront cost is critical in designing custom chips.  
**Custom Chips in Automakers**  
Automakers such as Tesla and General Motors Cruise are progressively creating their own chips to replace merchant solutions. This development reflects bespoke chips' increased relevance to specific automotive applications (Morgan Stanley Research, 2024).  
In conclusion, the investor report illuminates critical advances in the semiconductor business. Tesla's Dojo and the emergence of bespoke AI ASICs present intriguing potential and challenges to investors. As technology advances, the semiconductor business remains a dynamic and fascinating investment opportunity.

![](/assets/blog/b1.png)

Morgan Stanley Research. (2023). Update Investor Presentation \| Asia Pacific Friday New Economy Webcast: 5G, AI and China's Semiconductor Materials Localization Outlook.


## 2024 August 11 — Thoughts on Verification Engineering

![](/assets/blog/b2.png)

Hardware verification is an important process to determine the functionality of the circuitry. Verification can act as a steppingstone for getting into the design phase for engineers applying for jobs. 

**Before supplying power to the circuit board**  
1. Check if all the wirings are correct It is crucial to check the schematic diagram, and the first check focuses on whether the power supply of the chip and the network nodes are correctly labeled, and also pay attention to whether the network nodes overlap.  Another key point is the package of the original, the model of the package, the pin sequence of the package. Check whether the wires are correctly connected, including wrong lines, few lines, and multiple lines.  
There are usually two ways to check the wires:  
    - Check the installed wire according to the circuit diagram, and check the installed wire one by one according to the circuit connection in a certain order;  
    - According to the actual wire comparison schematic, the component as the center to check the wire. Check the wiring of each component pin once, and check whether each place exists on the circuit diagram.

2. Check if the power supply is short circuited. Do not power on before debugging, use a multimeter to measure the input impedance of the power supply, this is a necessary step! If the power supply is short circuited, it will cause the power supply to burn out or worse. When it comes to the power supply part, a 0 ohm resistance can be used as a debugging method. Do not weld the resistor before power-on. Check that the voltage of the power supply is normal, and then weld the resistor on the PCB to supply power to the rest of the circuit, so as not to burn the chip of the rear unit due to the abnormal voltage of the power supply. Add protective circuits to the circuit design, such as using components such as recovery fuses.

3. Check the installation of components. It is mainly to check the polar components, such as light-emitting diodes, electrolytic capacitors, rectifier diodes, etc., and whether the pins of the transistor correspond. For the triode, the same function of the different manufacturers of the pin ordering is also different, it is best to use a multimeter test.  
Perform an open circuit and short circuit test first to ensure that no short circuit occurs after power-on. If the test point is set up right, you can do more with less. The use of 0 ohm resistors is also sometimes advantageous for high-speed circuit testing.

**Power on Testing**  
1. Power observation: do not rush to measure electrical indicators after power, but to observe whether the circuit is abnormal, such as whether there is smoke, whether there is abnormal smell, hand touch integrated circuit packaging, whether hot and so on. If an abnormal phenomenon occurs, the power supply should be turned off immediately, and then powered on after the fault is rectified.

2. Static debugging: Static debugging generally refers to the DC test carried out without input signal, or only add a fixed level signal under the condition of the multimeter to measure the potential of each point in the circuit, through the comparison with the theoretical estimate, combined with the analysis of the circuit principle, to determine whether the DC working state of the circuit is normal, and timely find the circuit has been damaged or in the critical working state of the components. By replacing the device or adjusting the circuit parameters, the DC working state of the circuit can meet the design requirements.

3. Dynamic debugging: dynamic debugging is carried out on the basis of static debugging, in the input end of the circuit to add the appropriate signal, according to the direction of the signal, the sequence detection of the output signal of each test point, if found abnormal phenomenon, should analyze the cause, and troubleshoot, and then debug until meet the requirements.  
Do not rely on feelings during the test, always observe with the aid of instruments. When using an oscilloscope, it is best to put the signal input mode of the oscilloscope in the "DC" mode, and through the DC coupling mode, the AC and DC components of the signal under test can be observed at the same time. Through debugging, finally check whether the various indicators of the function block and the whole machine (such as the amplitude of the signal, waveform shape, phase relationship, gain, input impedance and output impedance, etc.) meet the design requirements, if necessary, and then further put forward reasonable amendments to the circuit parameters.

**Other work in electronic circuit debugging**  
1, Determine the test point: according to the working principle of the system to be adjusted to develop debugging steps and measurement methods, determine the test point, and mark the position on the board, make debugging data record forms.  
2, set up a debugging workbench: the workbench is equipped with the required debugging instrument, the instrument should be easy to operate, easy to observe. Special tip: In the production and debugging, be sure to arrange the workbench clean and tidy.  
3, select the measuring instrument: for the hardware circuit, the system should be tuned to select the measuring instrument, the accuracy of the measuring instrument should be better than the measured system; For software debugging, a microcomputer and a development device should be equipped.  
4, debugging sequence: the debugging sequence of the electronic circuit is generally carried out in accordance with the signal flow direction, and the output signal of the previously debuggable circuit is used as the input signal of the last level, creating conditions for the final regulation.  
5, overall debugging: the selection of programmable logic devices to achieve the digital circuit, should complete the programmable logic device source file input, debugging and download, and programmable logic devices and analog circuits connected into the system, overall debugging and result testing.

In the debugging process, it is necessary to carefully observe and analyze the experimental phenomenon, and make a good record to ensure the integrity and reliability of the experimental data.

![](/assets/blog/b3.png)

**Precautions in circuit debugging**  
Whether the debugging result is correct or not is largely affected by the correct test quantity and test accuracy. In order to ensure the results of the test, we must reduce the test error and improve the test accuracy, so we need to pay attention to the following points:  
1. Use the grounding terminal of the test instrument correctly. The overall grounding end should be connected together with the grounding end of the amplifier, otherwise the interference introduced by the instrument housing will not only change the working state of the amplifier, but also make the test result error.  
According to this principle, when debugging the emitter bias circuit, if the Vce needs to be tested, the two ends of the instrument should not be directly connected to the collector and the emitter, but should be measured respectively to the ground Vc and Ve, and then the two are subtracted. If using a dry battery powered multimeter test, because the two inputs of the meter are floating, it is allowed to directly straddle between the test points.

2. The input impedance of the instrument used to measure the voltage must be much greater than the equivalent impedance at the point being measured. If the input impedance of the test instrument is small, it will cause shunt during measurement, which will bring great errors to the test results.

3, the bandwidth of the test instrument must be greater than the bandwidth of the circuit under test.

4. Select the test point correctly. When the same measuring instrument is used for measurement, the error caused by the internal resistance of the instrument will be very different.

5, the measurement method should be convenient and feasible. When it is necessary to measure the current of a circuit, it is generally possible to measure the voltage without measuring the current, because the voltage does not need to change the circuit. If you need to know the current value of a branch, you can measure the voltage at both ends of the resistance on the branch and get it after conversion.

6, debugging process, not only to carefully observe and measure, but also good at recording. The contents recorded include experimental conditions, observed phenomena, measured data, waveform and phase relationships, etc. Only when a large number of reliable experimental records are compared with the theoretical results, can the circuit design problems be found and the design scheme be improved.

**Troubleshooting during debugging**  
1, the general method of fault inspection  
For a complex system, it is not easy to accurately find faults in a large number of components and lines. The general fault diagnosis process starts from the fault phenomenon, makes analysis and judgment through repeated testing, and gradually finds out the fault.

2. Fault symptoms and causes of the fault  
1) Common fault phenomenon: the amplifier circuit has no input signal, and there is an output waveform. The amplifier circuit has an input signal, but no output waveform, or the waveform is abnormal. The series voltage regulator has no voltage output, or the output voltage is too high and cannot be adjusted, or the output voltage regulator performance deteriorates, and the output voltage is unstable. Oscillation circuit does not produce oscillation, the counter waveform is unstable and so on.

2) The cause of the failure: after a period of time, the product fails, which may be damaged components, short circuit and open connections, or changes in conditions, etc.

3, check the general method of failure  
1) Direct observation method: check whether the selection and use of the instrument is correct, and whether the grade and polarity of the power supply voltage meet the requirements; Whether the polar element pins are connected correctly, whether there are wrong connections, missed connections and mutual collisions. Whether the wiring is reasonable; Whether the printed plate has a short wire break, and whether the resistance and capacitor are burnt and exploded. Power to observe whether the components are hot, smoking, transformer is not burnt, electron tube, oscilloscope tube filament is bright, there is no high voltage ignition.  
2) Use a multimeter to check the static working point: the power supply system of the electronic circuit, the DC working state of the semiconductor transistor and the integrated block (including the unit, the device pin, the power supply voltage), the resistance value in the line can be measured by a multimeter. When the measured value differs greatly from the normal value, the fault can be found through analysis.  
By the way, the static operating point can also be determined with the oscilloscope "DC" input mode. The advantage of oscilloscope is that the internal resistance is high, and the signal waveform on the DC working state and the measured point can be seen at the same time, as well as possible interference signals and noise voltage, which is more conducive to fault analysis.

3) Signal tracing method: For a variety of more complex circuits, a signal of a certain amplitude and an appropriate frequency can be accessed at the input end (for example, for a multistage amplifier, a sinusoidal signal of f,1000 HZ can be accessed at the input end), and the oscilloscope is used to observe the waveform and amplitude changes step by step from the front stage to the back stage (or vice versa), such as which level is abnormal, the fault is at the level.

4) Comparison method: When a circuit is suspected to have a problem, the parameters of this circuit can be compared with the same normal parameters (or theoretical analysis of current, voltage, waveform, etc.) to find out the abnormal situation in the circuit, and then analyze and judge the fault point.

5) Component replacement method: Sometimes the fault is hidden and can not be seen at a glance, such as when you have an instrument of the same model as the faulty instrument, you can replace the corresponding parts of the faulty instrument in the instrument components, components, plug-in boards, etc., in order to reduce the fault scope and find the fault source.

6) Bypass method: When there is a parasitic oscillation phenomenon, you can use the appropriate capacity of the capacitor, select the appropriate checkpoint, the capacitor temporarily straddles between the checkpoint and the reference ground point, if the oscillation disappears, it indicates that the oscillation is generated near this or in the previous circuit. Otherwise, it's in the back. Move the checkpoint. The bypass capacitance should be appropriate, not too large, as long as the harmful signal can be better eliminated.

7) Short circuit method: It is a method to take a temporary short circuit to find a fault. The short-circuit method is the most effective method to check the open-circuit fault. However, it should be noted that the power supply (circuit) can not use short circuit method.

8) Open circuit method: The open circuit method is the most effective for checking short circuit faults. The open circuit method is also a method to gradually reduce the scope of the suspected fault points. For example, if a regulated power supply is connected to a circuit with a fault, so that the output current is too large, we take the method of turning off a branch of the circuit in turn to check the fault. If the current returns to normal after the branch is disconnected, the fault occurs in this branch.

In actual debugging, there are many ways to find the cause of the fault, and the above only lists several common methods. The use of these methods can find the fault point with one method for simple faults, but for more complex faults, it is necessary to take a variety of methods to complement and cooperate with each other to find the fault point. In general, the usual way to find a fault is:

1) Use direct observation method to eliminate obvious faults.  
2) Then use a multimeter (or oscilloscope) to check the static working point.  
3) Signal tracing method is a simple and intuitive method that is generally applicable to various circuits and is widely used in dynamic debugging.


## 2024 May 02 — Product & Consumer Demand

Product & consumer demand 

![](/assets/blog/b4.png)