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

- **Parameters to take note off**
- Width, Length, Thickness: Surface Area
- Number of Fins
- Temperature Difference between heat sink and surroundings
- Convective Heat Transfer Coefficient

- ## For Cold Water Running Through Copper Tubes
