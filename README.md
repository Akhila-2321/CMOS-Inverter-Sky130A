
# CMOS Inverter Design and Physical Verification Using SKY130A

## Project Overview

This project focuses on the design, simulation, and physical implementation of a CMOS Inverter using the SKY130A technology.

The design is created using Xschem, circuit simulation is performed using NGSpice, and physical layout implementation and design rule verification are carried out using Magic VLSI.

A CMOS inverter is a basic digital logic circuit that produces the complement of its input signal. It consists of one PMOS transistor and one NMOS transistor connected together.

The main objective of this project is to understand CMOS inverter circuit design, prepare the schematic and testbench, verify its operation through transient simulation, and perform physical layout and verification.

---

## Tools and Technologies Used

- **Xschem** – Used for drawing the CMOS inverter schematic and creating the testbench.
- **NGSpice** – Used for circuit simulation and waveform analysis.
- **SKY130A PDK** – Open-source 130 nm process design kit used for the CMOS design.
- **Magic VLSI** – Used for physical layout implementation and DRC verification.
- **Netgen** – Used for Layout Versus Schematic (LVS) verification.
- **Ubuntu** – Linux environment for VLSI design and simulation.

---

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

---

# Design and Implementation

## 1. CMOS Inverter Schematic Design

The CMOS inverter schematic was created using Xschem.

The circuit contains one PMOS transistor and one NMOS transistor. Their gates are connected to the input, while their drains are connected to the output. The PMOS source is connected to VDD, and the NMOS source is connected to GND.

**Output 1: CMOS Inverter Schematic**

<img width="960" height="540" alt="CMOS Inverter Schematic" src="https://github.com/user-attachments/assets/dd50e9e3-a468-4c7f-9ff2-34a9c5c1e707" />

---

## 2. Testbench Creation

A testbench was created in Xschem to verify the functionality of the CMOS inverter.

The testbench includes:

- DC supply voltage of 1.8 V.
- Input pulse signal.
- CMOS inverter circuit.
- Simulation setup for transient analysis.

The input signal is applied to the inverter, and the output response is observed during simulation.

**Output 2: CMOS Inverter Testbench**

<img width="960" height="540" alt="CMOS Inverter Testbench" src="https://github.com/user-attachments/assets/6b0c47c6-7ad7-4575-ad34-860d30d9671f" />

---

## 3. Transient Simulation Using NGSpice

The designed testbench was simulated using NGSpice.

Transient analysis was performed to observe how the output changes with respect to the input signal.

### Simulation Observations

- When the input is LOW, the output is HIGH.
- When the input is HIGH, the output is LOW.
- The output waveform is the logical complement of the input waveform.

**Output 3: NGSpice Transient Simulation**

<img width="960" height="540" alt="NGSpice Transient Waveform" src="https://github.com/user-attachments/assets/d7b3cd2a-cbe7-467e-955e-f28e7bde038f" />

---

## 4. CMOS Inverter Physical Layout Using Magic VLSI

The CMOS inverter physical layout was developed using Magic VLSI with the SKY130A technology.

The transistor-level schematic was translated into a physical layout using technology-specific fabrication layers.

### 4.1 Physical Layout Structure

The CMOS inverter layout consists of:

- PMOS transistor placed inside the N-well region.
- NMOS transistor placed in the substrate region.
- Polysilicon gate connections for the common input.
- Drain connections combined to form the output.
- Metal interconnections for electrical connectivity.
- VDD and VSS power connections.

### 4.2 Layout Implementation

Magic VLSI was used to create the physical geometry of the CMOS inverter.

The layout uses appropriate SKY130A technology layers, including:

- N-well.
- Active diffusion.
- Polysilicon.
- Metal interconnect layers.
- Contact and via layers.

### 4.3 Complete CMOS Inverter Layout

The PMOS and NMOS transistor structures are integrated with the input, output, power and ground connections to form the CMOS inverter layout.

**Output 4: CMOS Inverter Physical Layout**

<img width="960" height="540" alt="CMOS Inverter Physical Layout" src="https://github.com/user-attachments/assets/b153520b-b166-4f47-a100-8af2d8e5fde3" />


---

## 5. Design Rule Check (DRC) Using Magic VLSI

Design Rule Check was performed using Magic VLSI with the SKY130A technology rules to verify the physical layout against fabrication constraints.

The layout was checked for spacing, width, enclosure and other technology-specific design rule violations.



### DRC Verification Result

The DRC verification was successfully completed with **zero violations**.

**DRC Result: 0 Errors**



**Status: Completed – 0 DRC Violations.**

---

## 6. SPICE Netlist Extraction

The physical layout will be extracted into a SPICE-compatible netlist using Magic VLSI.

The extracted netlist will be used for further electrical verification and post-layout simulation.

**Status: Pending.**

---

## 7. Layout Versus Schematic (LVS) Verification

LVS verification will be performed using Netgen to compare the extracted physical layout netlist with the original CMOS inverter schematic netlist.

The objective is to verify that the physical layout maintains the intended transistor connectivity.

**LVS Verification Result**


**Status: Pending.**

---

## 8. Post-Layout Simulation

Post-layout simulation will be performed using NGSpice with the extracted physical layout netlist.

The simulation results will be compared with the pre-layout waveforms to study the effects of physical implementation and parasitic components on circuit behavior.

**Post-Layout Simulation**



**Status: Pending.**

---

## Results

The CMOS inverter was successfully designed and simulated using Xschem and NGSpice.

The transient waveform verifies the basic inverter operation. The output signal changes in the opposite direction to the input signal, confirming the expected functionality of the CMOS inverter.

The physical layout was implemented using Magic VLSI, and DRC verification was completed with zero violations.

The remaining stages involve SPICE netlist extraction, LVS verification and post-layout simulation.

---

## Current Project Status

| Task | Status |
|---|---|
| CMOS inverter schematic design | Completed |
| Symbol creation | Completed |
| Testbench creation | Completed |
| NGSpice transient simulation | Completed |
| Magic VLSI physical layout | Completed |
| DRC verification | Completed – 0 violations |
| SPICE netlist extraction | Pending |
| LVS verification | Pending |
| Post-layout simulation | Pending |

---

## Future Work

- Extract the physical layout into a SPICE-compatible netlist.
- Perform Layout Versus Schematic (LVS) verification using Netgen.
- Complete post-layout simulation using NGSpice.
- Compare pre-layout and post-layout simulation results.
- Analyze the impact of parasitic components on inverter performance.

---

## Conclusion

This project provides practical experience in CMOS inverter design and physical verification using SKY130A technology.

The schematic was developed using Xschem, and its electrical functionality was verified through transient simulation using NGSpice.

The physical layout was implemented using Magic VLSI, and the layout successfully passed Design Rule Check with zero violations.

The next phase focuses on netlist extraction, LVS verification and post-layout simulation to complete the CMOS inverter physical-design flow.

---

## Author

**Anugu Akhila**

VLSI Design | CMOS Technology | Physical Verification

---

## References

- [SkyWater SKY130 PDK](https://github.com/google/skywater-pdk)
- [Xschem](https://xschem.sourceforge.io/)
- [NGSpice](https://ngspice.sourceforge.io/)
- [Magic VLSI](http://opencircuitdesign.com/magic/)
- [Netgen](http://opencircuitdesign.com/netgen/)
