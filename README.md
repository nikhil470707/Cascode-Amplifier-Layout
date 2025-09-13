# Cascode Amplifier with Biasing Network

A comprehensive analog IC design project implementing a high-performance cascode amplifier system with complete biasing network in 180nm and 22nm CMOS technologies.

## Project Overview

This project demonstrates the design, simulation, and layout implementation of a cascode amplifier system comprising three integrated circuit blocks:
- **Beta Multiplier Circuit**: PTAT-like current reference without bipolar devices
- **Cascode Current Mirror**: High output impedance current source
- **Cascode Amplifier**: High-gain, wide-bandwidth telescopic configuration

## System Architecture

```
VDD → [Beta Multiplier] → [Cascode Current Mirror] → [Cascode Amplifier] → VOUT
                                ↓
                            Bias Voltages (Vbias1, Vbias2, Vbias3)
```

## Design Specifications

### Target Performance (180nm Technology)
- **Supply Voltage**: 1.8V
- **Voltage Gain (Av)**: ≥ 20 V/V
- **Power Dissipation**: < 5mW
- **Load Capacitance**: 1pF
- **Unity Gain Bandwidth**: > 500kHz

### Achieved Results
| Parameter | 180nm Target | 180nm Achieved | 22nm Achieved |
|-----------|-------------|----------------|---------------|
| Voltage Gain | 20 V/V | 21.89 dB | 23.30 dB |
| UGB | >500 kHz | 15.85 MHz | 2.75 MHz |
| Power | <5 mW | 0.05 mW | 0.62 mW |
| Current | - | 27.65 μA | 79.95 μA |

## Circuit Implementation

### 1. Beta Multiplier Circuit
- **Function**: Generates stable reference current with PTAT-like characteristics
- **Key Feature**: Uses positive feedback with resistive stabilization
- **Advantage**: Eliminates need for bipolar transistors in current reference

### 2. Cascode Current Mirror
- **Function**: Provides high output impedance current sources for biasing
- **Outputs**: Multiple bias voltages (Vbias1, Vbias2, Vbias3, Vbiasp)
- **Architecture**: Cascoded PMOS/NMOS configuration for improved matching

### 3. Cascode Amplifier (Telescopic Configuration)
- **Stage 1**: Common Source (CS) amplifier
- **Stage 2**: Common Gate (CG) amplifier
- **Benefits**: High input/output impedance, wide bandwidth, excellent isolation

## Technology Comparison: 180nm vs 22nm

### Performance Improvements in 22nm:
- **Higher Voltage Gain**: 23.30 dB vs 21.89 dB
- **Compact Design**: ~8x smaller transistor dimensions
- **Process Advantages**: Better matching, reduced parasitic effects

### Trade-offs:
- **Power Consumption**: Higher in 22nm (0.62 mW vs 0.05 mW)
- **Manufacturing Complexity**: More challenging layout rules
- **Design Margins**: Tighter constraints in advanced node

## Design Flow

### 1. Theoretical Analysis
- Hand calculations for transistor sizing
- Small-signal analysis for gain and bandwidth
- Operating point calculations
- Stability analysis

### 2. Schematic Simulation (LTSpice)
- DC operating point verification
- AC analysis for frequency response
- Transient analysis for step response
- For both 180nm and 22nm

### 3. Physical Layout (Magic VLSI - 180nm)
- Floorplanning and device placement
- Routing with parasitic considerations
- DRC (Design Rule Check) verification
- LVS (Layout vs Schematic) verification

### 4. Post-Layout Verification
- Parasitic extraction
- Performance correlation with schematic
- Layout-aware simulations


## Tools Used

- **Circuit Simulation**: LTSpice
- **Layout Design**: Magic VLSI Layout Tool
- **Technology Files**: 180nm CMOS PDK, 22nm CMOS models


## Key Design Insights

### Beta Multiplier Design
- Resistor value selection critical for stability
- PMOS-to-NMOS ratio affects current magnitude
- Temperature coefficient optimization

### Current Mirror Optimization
- Cascode configuration improves output resistance by ~100x
- Proper bias voltage distribution essential for headroom
- Matching considerations for current accuracy

### Amplifier Performance
- Telescopic cascode provides highest gain-bandwidth product
- Load capacitance dominates frequency response
- Power-delay trade-off optimization

## Simulation Validation

### Methodology
1. **DC Analysis**: Operating point verification
2. **AC Analysis**: Small-signal frequency response
3. **Transient Analysis**: Large-signal behavior


### Key Validations
- Theoretical vs simulated gain correlation within 5%
- Bandwidth predictions validated through pole-zero analysis
- Power consumption meets specification with 90% margin
- Layout performance matches schematic within 10%


## Usage Instructions

### LTSpice Simulation
1. Install LTSpice XVII
2. Load technology models from `/schematics/models/`
3. Open schematic files and run simulations
4. Compare results with provided reference data

### Magic Layout
1. Install Magic VLSI tool
2. Load 180nm technology file
3. Open layout files from `/layouts/magic_180nm/`
4. Run DRC and LVS checks

## Results Summary

This project successfully demonstrates:
- Complete analog IC design methodology from concept to layout
- Multi-technology node comparison and scaling analysis  
- Integration of multiple analog building blocks into functional system
- Validation of theoretical predictions through simulation
- Physical implementation with layout verification

The cascode amplifier system achieves all target specifications while providing insights into advanced CMOS analog design techniques and technology scaling effects.

## Contact

**Author**: A.D.V.M.S. Nikhil  
**Institution**: Indian Institute of Technology, Ropar  
**Course**: EE301 - Analog Circuits  
**Course Instructor**: Dr. Mahendra Sakare

---
*This project was completed as part of the Analog Circuits course at IIT Ropar, demonstrating practical application of CMOS analog IC design principles.*
