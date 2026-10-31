# CMOS Inverter Design and Physical Verification Using SKY130A

## Project Overview

This project focuses on the design, physical implementation, verification, and post-layout simulation of a CMOS Inverter using the open-source SKY130A 130 nm Process Design Kit (PDK).

The CMOS inverter is designed using Xschem, and its pre-layout functionality is verified using NGSpice. The physical layout is created using Magic VLSI, followed by Design Rule Check (DRC) and Layout Versus Schematic (LVS) verification.

After successful physical verification, the layout is extracted into a SPICE netlist, including parasitic capacitances, and post-layout transient simulation is performed using NGSpice.

The project demonstrates the complete CMOS inverter design flow, from schematic capture to physical verification and post-layout analysis.

## Project Objectives

- Understand the working principle of a CMOS inverter.
- Design a CMOS inverter schematic using Xschem.
- Perform pre-layout transient simulation using NGSpice.
- Create the physical layout using Magic VLSI.
- Verify the layout using DRC.
- Perform LVS verification using Netgen.
- Extract parasitic capacitances from the physical layout.
- Perform post-layout simulation and analyze the input and output waveforms.

## Tools and Technologies Used

| Tool / Technology | Purpose |
|---|---|
| Ubuntu | Development environment |
| Xschem | Schematic design |
| NGSpice | Pre-layout and post-layout simulation |
| Magic VLSI | Physical layout design and DRC |
| Netgen | LVS verification |
| SKY130A PDK | 130 nm CMOS technology |
| Git and GitHub | Version control and project documentation |

## 1. CMOS Inverter Theory

A CMOS inverter is a fundamental digital logic circuit that produces an output complementary to its input.

It consists of two MOSFET transistors:

- PMOS transistor connected to the positive supply voltage (VDD).
- NMOS transistor connected to ground (VSS).
- Both transistor gates are connected to the input.
- Both transistor drains are connected to the output.

### Working Principle

**Case 1: Input LOW (0 V)**

- PMOS transistor turns ON.
- NMOS transistor turns OFF.
- Output becomes HIGH (1.8 V).

**Case 2: Input HIGH (1.8 V)**

- PMOS transistor turns OFF.
- NMOS transistor turns ON.
- Output becomes LOW (0 V).

Therefore, the output is always the logical complement of the input.

## 2. Inverter Design Specifications

The CMOS inverter is implemented using SKY130A transistor models.

| Parameter | PMOS | NMOS |
|---|---|---|
| Model | sky130_fd_pr__pfet_01v8 | sky130_fd_pr__nfet_01v8 |
| Width (W) | 3 µm | 4.5 µm |
| Length (L) | 0.18 µm | 0.18 µm |
| Supply voltage | 1.8 V | 1.8 V |

## 3. Schematic Design Using Xschem

The CMOS inverter schematic is created using Xschem with the SKY130A PMOS and NMOS transistor models.

The PMOS source is connected to VDD, and the NMOS source is connected to VSS. Both gates share the input signal, and both drains are connected to the output.

The schematic is used as the reference circuit for simulation and physical verification.

**Output 1: CMOS Inverter Schematic**
<img width="960" height="540" alt="cmos_inverter_schematic png" src="https://github.com/user-attachments/assets/dfda9da0-42da-4796-b8c7-ddc2517385d3" />


## 4. Pre-Layout Simulation Using NGSpice

Before creating the physical layout, the schematic is simulated using NGSpice to verify the inverter's functionality.

### Testbench Configuration

- Supply voltage: 1.8 V
- Input signal: Pulse waveform (0–1.8 V)
- Analysis: Transient simulation
- Simulator: NGSpice

### Simulation Observations

- When the input is LOW, the output is HIGH.
- When the input is HIGH, the output is LOW.
- The output waveform is complementary to the input waveform.

**Output 2: Pre-Layout Transient Simulation**

<img width="960" height="540" alt="inverter_testbench png" src="https://github.com/user-attachments/assets/76fc4d94-90c3-4eb7-953b-c25471d90359" />


## 5. Physical Layout Design Using Magic VLSI

The CMOS inverter physical layout is created using Magic VLSI with the SKY130A technology.

The layout contains the PMOS and NMOS transistor structures, diffusion regions, polysilicon gates, contacts, and metal interconnections.

The physical connections are established to implement the inverter circuit with the required power, ground, input, and output terminals.

### Layout Design Features

- PMOS and NMOS transistor implementation.
- SKY130A technology layers.
- Metal interconnections.
- VDD and VSS power connections.
- Common input and output connections.

**Output 3: CMOS Inverter Physical Layout**

<img width="960" height="540" alt="CMOS Inverter Physical Layout" src="https://github.com/user-attachments/assets/eea81c0f-2364-4eaf-bd13-b100516233e6" />


## 6. Design Rule Check (DRC)

Design Rule Check is performed using Magic VLSI to verify that the physical layout follows the manufacturing design rules defined by the SKY130A PDK.

DRC checks the layout for issues such as spacing, width, enclosure, and other technology-specific geometric constraints.

### DRC Commands

Inside the Magic command window:

```tcl
drc check
drc count
drc why
```

### DRC Result

```text
DRC Errors: 0
```

The final layout passed the DRC verification with zero reported violations.






## 7. Layout Extraction Using Magic

After successful DRC verification, the physical layout is extracted into a SPICE netlist.

The extraction process identifies the transistor devices and electrical connections. Parasitic capacitances associated with the physical layout are also extracted for post-layout simulation.
<img width="960" height="540" alt="Layout Extraction" src="https://github.com/user-attachments/assets/329f090b-f80e-4537-8e5b-25efa68bfe77" />


### Extraction Commands

```tcl
extract all
ext2spice lvs
ext2spice cthresh 0
ext2spice -o cmos_inverter_postlayout.spice
```

### Extracted Netlist

The generated file is:

```text
cmos_inverter_postlayout.spice
```

The extracted netlist contains:

- PMOS transistor model.
- NMOS transistor model.
- Extracted circuit connections.
- Layout-related parasitic capacitances.
- 

## 8. Layout Versus Schematic (LVS) Verification Using Netgen

LVS verification is performed using Netgen to compare the extracted physical layout netlist against the reference schematic netlist.

The comparison verifies whether the transistor devices and electrical connectivity in the physical layout correspond to the original schematic.
<img width="960" height="540" alt="Layout Versus Schematic (LVS) Verification" src="https://github.com/user-attachments/assets/96387d95-c6cd-4d50-838e-6edfac5d9919" />


### LVS Verification Results

The final Netgen report confirms:

| Parameter | Layout | Schematic |
|---|---:|---:|
| PMOS devices | 1 | 1 |
| NMOS devices | 1 | 1 |
| Total devices | 2 | 2 |
| Number of nets | 6 | 6 |

### Final LVS Result

```text
Circuit 1 contains 2 devices.
Circuit 2 contains 2 devices.

Circuit 1 contains 6 nets.
Circuit 2 contains 6 nets.

Final result:
Circuits match uniquely.
```

The successful LVS result confirms that the extracted layout matches the reference schematic.



## 9. Post-Layout Simulation Using NGSpice

After successful DRC and LVS verification, post-layout simulation is performed using NGSpice.

The extracted SPICE netlist from Magic is used for simulation. Unlike pre-layout simulation, the extracted netlist includes parasitic capacitances associated with the physical layout.

The SKY130A transistor models are loaded using the TT (Typical-Typical) process corner.
<img width="960" height="540" alt="Post-Layout Simulation Using NGSpice" src="https://github.com/user-attachments/assets/d01e384c-326d-496d-bd44-1ab74e3a43b5" />


### Post-Layout Simulation Configuration

| Parameter | Value |
|---|---|
| Technology | SKY130A |
| Process corner | TT |
| Supply voltage | 1.8 V |
| Input signal | Pulse waveform |
| Input voltage range | 0–1.8 V |
| Simulation type | Transient analysis |
| Simulator | NGSpice |




### Simulation Steps

The extracted netlist is included in the post-layout testbench along with the SKY130A model library, supply voltage, and input pulse source.

The transient simulation is executed using NGSpice.

```bash
ngspice postlayout_tb.spice
```

The input and output signals are observed using:

```spice
plot v(in) v(out)
```

### Post-Layout Simulation Observations

- The input signal switches between 0 V and 1.8 V.
- When the input is HIGH, the output becomes LOW.
- When the input is LOW, the output becomes HIGH.
- The extracted parasitic capacitances are included in the simulation.
- The output maintains the expected inverted response.

**Output 6: Post-Layout Transient Simulation**

<img width="546" height="448" alt="Post-Layout Simulation Configuration" src="https://github.com/user-attachments/assets/83301593-a357-4f84-a320-2e4d64ed735f" />

## 10. Pre-Layout vs Post-Layout Simulation

| Parameter | Pre-Layout | Post-Layout |
|---|---|---|
| Netlist | Schematic SPICE | Magic-extracted SPICE |
| Simulator | NGSpice | NGSpice |
| Supply voltage | 1.8 V | 1.8 V |
| Input range | 0–1.8 V | 0–1.8 V |
| Parasitic capacitances | Not included from layout extraction | Included |
| Analysis | Transient | Transient |
| Expected logic | Inverter operation | Inverter operation |

Post-layout simulation provides a more physically representative view of circuit behavior because it considers parasitic capacitances introduced by the layout.

## 11. Final Project Results

The CMOS inverter was successfully designed, physically implemented, and verified using the SKY130A PDK.

The final verification results are:

| Verification Stage | Result |
|---|---|
| Xschem schematic design | Completed |
| Pre-layout NGSpice simulation | Completed |
| Magic physical layout | Completed |
| DRC verification | 0 violations |
| Layout extraction | Completed |
| Netgen LVS verification | Circuits match uniquely |
| Post-layout NGSpice simulation | Completed |

## 12. Key Learnings

1. Understood the working principle and transistor-level implementation of a CMOS inverter.
2. Learned schematic capture and SPICE netlist generation using Xschem.
3. Gained practical experience with transient simulation using NGSpice.
4. Understood the physical implementation of PMOS and NMOS devices using Magic VLSI.
5. Learned to identify and resolve physical layout connectivity issues during LVS debugging.
6. Understood the importance of DRC and LVS in physical verification.
7. Learned SPICE netlist extraction and parasitic capacitance analysis.
8. Understood the differences between pre-layout and post-layout simulation.

## 13. Conclusion

This project demonstrates the complete design and physical verification flow of a CMOS inverter using the SKY130A 130 nm technology.

The schematic was designed using Xschem, and its functionality was verified through pre-layout simulation using NGSpice. The physical layout was implemented using Magic VLSI and successfully passed DRC verification with zero violations.

LVS verification using Netgen confirmed that the extracted layout and reference schematic match uniquely. Finally, post-layout simulation was performed using the extracted SPICE netlist, including layout parasitic capacitances.

Through this project, practical knowledge was gained in CMOS circuit design, physical layout implementation, verification, parasitic extraction, and post-layout simulation using open-source EDA tools.

## 14. References

- [SkyWater SKY130 Open-Source PDK](https://github.com/google/skywater-pdk)
- [Open_PDKs](https://github.com/RTimothyEdwards/open_pdks)
- [Xschem – Schematic Capture Tool](https://github.com/StefanSchippers/xschem)
- [Magic VLSI Layout Tool](http://opencircuitdesign.com/magic/)
- [Netgen LVS](http://opencircuitdesign.com/netgen/)
- [NGSpice Circuit Simulator](https://ngspice.sourceforge.io/)

## Author

**Anugu Akhila**

Project: CMOS Inverter Design and Physical Verification Using SKY130A

GitHub: [Akhila-2321](https://github.com/Akhila-2321)

Repository: [CMOS-Inverter-Sky130A](https://github.com/Akhila-2321/CMOS-Inverter-Sky130A)
