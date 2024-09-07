# Boost PFC Converter Design

The project presents the simulation of a Boost Power Factor Correction (PFC) converter. The converter is designed to convert AC power to regulated DC power with high efficiency and improved power factor. This design can be applied in various applications where power factor correction and DC voltage regulation are required, such as in power supplies, industrial applications, and renewable energy systems.

## Project Specifications

- **Peak AC Line Voltage (𝑉𝑝𝑘):** 325 V
- **Output DC Voltage (𝑉𝑑𝑐):** 400 V
- **Output Power (𝑃OUT):** 7 kW
- **Line Frequency (𝑓𝑙𝑖𝑛𝑒):** 50 Hz
- **Switching Frequency (𝑓𝑠):** 100 kHz
- **Boost Inductance:** 500 μH
- **Peak-to-Peak Voltage Ripple in Output Capacitor:** 8 V
- **Feedback Resistance of Current Loop (𝑅𝑓):** 0.05 Ω
- **Control Coefficient (𝑘𝑥):** 0.01
- **Pulse Width Modulator (PWM) Peak Voltage:** 5 V
- **Reference Voltage for Voltage Loop (𝑣𝑟𝑒𝑓,𝑣):** 5 V

## Key Features

- **Power Factor Correction:** Ensures the input current is sinusoidal and in phase with the input voltage, improving power quality.
- **High Efficiency:** Uses a high switching frequency of 100 kHz for reduced component sizes and higher efficiency.
- **Stable DC Output:** Maintains a regulated 400 V DC output with minimal ripple.

## Design Overview

The Boost PFC converter operates by boosting the input AC voltage to a higher regulated DC voltage, while correcting the power factor by shaping the input current to follow the input voltage waveform. The key components and parameters include:

- **Boost Inductor:** Designed with a value of 500 μH to limit the current ripple and ensure efficient energy transfer.
- **Capacitor Sizing:** The output capacitor is sized to limit the peak-to-peak voltage ripple to 8 V, ensuring a stable DC output.
- **Current and Voltage Loops:** Feedback control is implemented using current and voltage loops to maintain the desired output voltage and protect against overcurrent conditions.
  
## Control Strategy

- The PFC converter uses a **current loop** feedback to regulate the inductor current with a feedback resistance of 0.05 Ω.
- A **voltage loop** is used to regulate the output voltage at 400 V, with a reference voltage (𝑣𝑟𝑒𝑓,𝑣) of 5 V. A proportional-integral (PI) controller with **Anti Windup** technique is implemented for better regulation.
- A notch filter to filter out the **2\omega** in the feedback path so that the PI controller avoids generating response to 2\omega component which can lead to harmonics in input current.
- **Pulse Width Modulation (PWM)** is used to control the switching of the power MOSFET, with a peak modulation voltage of 5 V.
