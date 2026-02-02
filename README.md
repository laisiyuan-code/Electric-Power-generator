# Cold-Water-Always

## Overview
This project is a simple cooling system designed to lower the temperature of water in a bottle using a heat transfer chain powered by solar. Coolant circulates through copper coil wrapped around the water bottle, transferring heat away.

## Design Concept
Coolant is pumped through a copper coil wrapped around the water bottle. As coolant flows, it absorbs heat from the bottle. The IPA then moves into a reservoir which is cooled by a fan. The fan removes heat from the coolant, allowing it to recirculate and continue cooling the bottle.

## Key Considerations
- **Thermal Conductivity**: Copper is chosen for its excellent heat transfer, ensuring efficient cooling from bottle to coolant.
- **Safety**: Coolant is toxic, so care is taken with sealed tubing and no food sources.
- **Alternative Coolants**: While Coolant is effective, a water-glycol mix could be safer, reducing flammability.
- **Fan Cooling Efficiency**: The fan and radiator need to dissipate heat at a rate that keeps the coolant cool enough for the next cycle.

## Safety Guidelines and standards
-

## Parameters


#### Coolant Evaluation
| no. |Coolant Type      | How cold can it get       | heat transfer speed  | Viscosity |
|:------------:|:-------------------:|:-----------------:|:----------------------:|:----:|

## Heat Transfer Equations
- ## For Air Across Heat Sink Fins

- **General Idea: Heat Transfer is generally by convection (in reality more complicated than that but for now take this)**
<img width="784" height="509" alt="image" src="https://github.com/user-attachments/assets/474447b1-96b8-49c4-a9fe-6d502ba4739d" />

- **General Fin Equations**
<img width="592" height="300" alt="image" src="https://github.com/user-attachments/assets/8d9c0c63-3e5e-485e-85c7-982251e38311" />
<img width="592" height="300" alt="image" src="https://github.com/user-attachments/assets/271e3db9-82ff-40b3-939e-8d9e9cc96d62" />

- **Fin Efficiency and Overall Effectiveness**
<img width="590" height="300" alt="image" src="https://github.com/user-attachments/assets/12aabf7f-a6e7-4f10-9292-5153b583a361" />
<img width="591" height="300" alt="image" src="https://github.com/user-attachments/assets/e877aa4d-403a-4103-9882-4bd2ae10efd9" />

- **Parameters to take note of**
- Width, Length, Thickness: Surface Area
- Number of Fins
- Temperature Difference between heat sink and surroundings
- Convective Heat Transfer Coefficient

- ## For Cold Water Running Through Copper Tubes

- **General Idea: Heat Transfer also by convection BUT also depends on the nature of flow (Like Turbulent vs Laminar etc.)**
<img width="794" height="440" alt="image" src="https://github.com/user-attachments/assets/116afd61-5b85-4e37-8765-6bdfb886921c" />

- **Determining Flow and the Temperature at which to evaluate the thermal properties of the material at**
<img width="593" height="300" alt="image" src="https://github.com/user-attachments/assets/54ac229f-8d3d-4273-9494-3864de04da84" />
<img width="593" height="300" alt="image" src="https://github.com/user-attachments/assets/682a0192-7c82-45a0-88f6-d40c72c2c343" />

- **Simplest Thermal Analysis (but unlikely to be similar to reality)**
<img width="847" height="430" alt="image" src="https://github.com/user-attachments/assets/5b3a5540-a4a6-4a62-aa8b-2b1a969eecb2" />

- **General Thermal Analysis**
<img width="529" height="300" alt="image" src="https://github.com/user-attachments/assets/1f61ce98-3f42-4c8d-84ce-bd97d2e9ccd0" />
<img width="529" height="300" alt="image" src="https://github.com/user-attachments/assets/7deb50fa-e5f9-4291-b53f-fca107575423" />

- **Parameters to take note of**
- Surface Area of fluid in contact with inner surface of tube
- Mass flow rate of fluid (essentially velocity)
- Convective Heat Transfer Coefficient
- Inlet and Outlet Temperature

