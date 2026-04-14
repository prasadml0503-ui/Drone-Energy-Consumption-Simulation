# Drone Energy System Simulation & Battery Sizing Tool

## Overview
This project is a physics-based simulation tool designed to estimate drone hover power requirements and evaluate battery performance. It uses aerodynamic models and system efficiency parameters to compute power consumption and predict flight endurance.

The tool is implemented using Python and Flask, providing an interactive interface for real-time analysis.

## Key Features
- Hover power estimation using aerodynamic principles  
- Battery sizing for target flight endurance (bisection method)  
- Endurance estimation for a given battery mass  
- Power breakdown across motor, ESC, and propeller losses  
- Real-time parameter tuning via API  

## Technologies Used
- Python  
- Flask (Backend API)  
- Mathematical modeling (aerodynamics & energy systems)  

## Core Concepts
The model is based on standard propeller and thrust equations:

- Thrust:  
  T = Ct × ρ × A × ω²  

- Power:  
  P = Cp × ρ × A × ω³  

Where:
- Ct = Thrust coefficient  
- Cp = Power coefficient  
- ρ = Air density  
- A = Propeller disc area  
- ω = Angular velocity  

## Working Principle

### 1. Hover Power Calculation
- Total drone weight is distributed across motors  
- Required thrust per motor is calculated  
- Angular velocity (ω) is derived using thrust equations  
- Mechanical power is computed using aerodynamic relations  
- Electrical power is obtained considering system efficiency  

### 2. Battery Sizing (Target Endurance Mode)
- Uses **bisection search algorithm**  
- Iteratively finds minimum battery mass required to meet target flight time  
- Compares:
  - Required energy = Power × Time  
  - Available energy = Battery mass × energy density  

### 3. Endurance Estimation Mode
- Computes achievable flight time for a given battery mass  
- Converts energy capacity into runtime based on power consumption  

### 4. Power Loss Analysis
Breaks total power into:
- ESC losses  
- Motor losses  
- Propeller losses  
- Useful thrust power  

## Input Parameters
- Number of motors  
- Frame, payload, and electronics mass  
- Propeller diameter  
- Thrust (Ct) and power (Cp) coefficients  
- Motor, ESC, and propeller efficiencies  
- Battery energy density and voltage  
- Air density  

## Results
The system provides:
- Total hover power requirement (W)  
- Battery mass required (kg)  
- Battery capacity (Ah)  
- Estimated flight endurance (minutes)  
- Total system mass  
- Efficiency metrics  
- Detailed power loss breakdown  

## Applications
- Drone design and preliminary sizing  
- Battery selection and performance analysis  
- Educational tool for UAV energy modeling  
- Rapid prototyping of aerial systems  

## Strengths of the Model
- Combines physics-based modeling with practical constraints  
- Uses iterative numerical methods (bisection search)  
- Accounts for real-world inefficiencies  
- Modular and extendable architecture  

## Limitations
- Assumes steady hover (no forward flight dynamics)  
- Relies on estimated aerodynamic coefficients (Ct, Cp)  
- Does not include environmental disturbances  

## Future Improvements
- Forward flight and dynamic modeling  
- Integration with real drone telemetry  
- GUI-based visualization dashboard  
- Multi-objective optimization (weight vs endurance)  
- Motor-propeller database integration  
