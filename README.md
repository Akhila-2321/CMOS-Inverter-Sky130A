# CMOS Inverter Design Using SKY130A

## Project Overview

This project focuses on the design and simulation of a CMOS Inverter using the SKY130A technology. The design is created using Xschem, and circuit simulation is performed using NGSpice.

A CMOS inverter is a basic digital logic circuit that produces the complement of its input signal. It consists of one PMOS transistor and one NMOS transistor connected together.

The main objective of this project is to understand CMOS inverter circuit design, prepare the schematic and testbench, and verify its operation through transient simulation.

## Tools and Technologies Used

- **Xschem** – Used for drawing the CMOS inverter schematic and creating the testbench.
- **NGSpice** – Used for circuit simulation and waveform analysis.
- **SKY130A PDK** – Open-source 130 nm process design kit used for the CMOS design.

## CMOS Inverter Theory

A CMOS inverter consists of two MOSFETs:

- PMOS transistor connected to VDD.
- NMOS transistor connected to GND.
- Both transistor gates are connected to the input.
- Both transistor drains are connected to the output.

### Working Principle

1. When the input is LOW (0 V), the PMOS transistor turns ON and the NMOS transistor turns OFF. Therefore, the output becomes HIGH (1.8 V).
2. When the input is HIGH (1.8 V), the PMOS transistor turns OFF and the NMOS transistor turns ON. Therefore, the output becomes LOW (0 V).

Thus, the output is always the opposite of the input.

## Design and Simulation Steps

### 1. CMOS Inverter Schematic Design

The CMOS inverter schematic was created using Xschem.

The circuit contains one PMOS transistor and one NMOS transistor. Their gates are connected to the input, while their drains are connected to the output. The PMOS source is connected to VDD, and the NMOS source is connected to GND.

**Output 1: CMOS Inverter Schematic**

<img width="960" height="540" alt="cmos_inverter_schematic png" src="https://github.com/user-attachments/assets/dd50e9e3-a468-4c7f-9ff2-34a9c5c1e707" />


### 2. Testbench Creation

A testbench was created in Xschem to verify the functionality of the CMOS inverter.

The testbench includes:
- DC supply voltage of 1.8 V.
- Input pulse signal.
- CMOS inverter circuit.
- Simulation setup for transient analysis.

The input signal is applied to the inverter, and the output response is observed during simulation.

**Output 2: CMOS Inverter Testbench**

<img width="960" height="540" alt="inverter_testbench png" src="https://github.com/user-attachments/assets/6b0c47c6-7ad7-4575-ad34-860d30d9671f" />


### 3. Transient Simulation Using NGSpice

The designed testbench was simulated using NGSpice.

Transient analysis was performed to observe how the output changes with respect to the input signal.

**Simulation Observations:**

- When the input is LOW, the output is HIGH.
- When the input is HIGH, the output is LOW.
- The output waveform is the logical complement of the input waveform.

**Output 3: NGSpice Transient Simulation**

<img width="960" height="540" alt="ngspice_transient_waveform png" src="https://github.com/user-attachments/assets/d7b3cd2a-cbe7-467e-955e-f28e7bde038f" />


## Results

The CMOS inverter was successfully designed and simulated.

The transient waveform verifies the basic inverter operation. The output signal changes in the opposite direction to the input signal, confirming the expected functionality of the CMOS inverter.

## Current Project Status

| Task | Status |
|---|---|
| CMOS inverter schematic design | Completed |
| Symbol creation | Completed |
| Testbench creation | Completed |
| NGSpice transient simulation | Completed |
| Layout design using Magic | Pending |
| DRC verification | Pending |
| LVS verification | Pending |

## Future Work

- Create the CMOS inverter layout using Magic.
- Perform Design Rule Check (DRC).
- Perform Layout Versus Schematic (LVS) verification.
- Complete layout extraction and post-layout simulation.

## Conclusion

This project helped in understanding the basic design and working principle of a CMOS inverter using SKY130A technology. The schematic was designed using Xschem, and its functionality was verified through transient simulation using NGSpice. The simulation results confirm the expected inverter operation.

## Author

**Anugu Akhila**

## References

- [SkyWater SKY130 PDK](https://github.com/google/skywater-pdk)
- [Xschem](https://xschem.sourceforge.io/)
- [NGSpice](https://ngspice.sourceforge.io/)
