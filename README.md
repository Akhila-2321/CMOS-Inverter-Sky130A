
# CMOS Inverter Design using SKY130A PDK

## 1. Project Overview

This project focuses on the design and simulation of a CMOS inverter using the SKY130A Process Design Kit (PDK).

The CMOS inverter is designed using PMOS and NMOS transistors. The schematic is created using Xschem, and transient simulation is performed using ngspice to verify the inverter functionality. The physical layout is being implemented using Magic VLSI.

## 2. Objectives

- To design a CMOS inverter using PMOS and NMOS transistors.
- To create the circuit schematic using Xschem.
- To perform transient simulation using ngspice.
- To analyse the input and output voltage waveforms.
- To implement the physical layout using Magic VLSI.
- To work with the SKY130A technology library.

## 3. Tools and Technologies Used

| Tool | Purpose |
|---|---|
| Xschem | Schematic Design |
| ngspice | Circuit Simulation |
| Magic VLSI | Physical Layout Design |
| SKY130A PDK | Technology Library |
| Ubuntu Linux | Development Environment |

## 4. CMOS Inverter Schematic Design

The CMOS inverter consists of two MOS transistors:

- PMOS transistor (M1) connected to VDD.
- NMOS transistor (M2) connected to VSS.
- Both gates are connected to the input (IN).
- Both drains are connected to the output (OUT).

The supply voltage used is 1.8V.

### Schematic Output

![CMOS Inverter Schematic](images/cmos_schematic.png)

## 5. Testbench Design

A testbench is created in Xschem to verify the functionality of the CMOS inverter.

Simulation parameters:

- Supply Voltage: 1.8V
- Input Signal: Pulse/Ramp Signal
- Analysis: Transient Analysis
- Simulation Tool: ngspice

### Testbench Output

![CMOS Inverter Testbench](images/testbench.png)

## 6. Transient Simulation using ngspice

Transient analysis is performed using ngspice to observe the CMOS inverter response.

### Simulation Results

- When the input voltage is LOW, the output voltage is HIGH.
- When the input voltage is HIGH, the output voltage is LOW.
- The output waveform represents the logical NOT operation of the input.

### Simulation Waveform

![ngspice Simulation Output](images/simulation_output.png)

## 7. Physical Layout using Magic VLSI

The physical layout of the CMOS inverter is being implemented using Magic VLSI with the SKY130A PDK.

The layout includes:

- PMOS and NMOS transistor structures.
- Input connection (IN).
- Output connection (OUT).
- Power supply connection (VDD).
- Ground connection (VSS).

### Initial Layout Output

![Magic CMOS Inverter Layout](images/magic_layout.png)

## 8. Project Progress

| Task | Status |
|---|---|
| CMOS Inverter Schematic | Completed |
| Testbench Design | Completed |
| ngspice Transient Simulation | Completed |
| Initial Magic Layout | In Progress |
| DRC Verification | Pending |
| Layout Extraction | Pending |
| LVS Verification | Pending |

## 9. Conclusion

The CMOS inverter schematic was successfully designed using Xschem, and its transient response was verified using ngspice.

The simulation confirms the expected inverter operation, where the output voltage is the logical complement of the input voltage.

The physical layout implementation using Magic VLSI and SKY130A PDK is currently in progress. DRC and LVS verification will be performed in the next stages.

## 10. Author

**Name:** Anugu Akhila

**Project Title:** CMOS Inverter Design using SKY130A PDK

**Domain:** VLSI Design and Physical Verification
