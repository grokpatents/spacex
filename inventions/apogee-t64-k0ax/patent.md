# Firmware-based adaptive MPPT reconfiguration system for photovoltaic roof tiles

## Abstract
A firmware update for solar roof tile inverters implements dynamic maximum power point tracking (MPPT) reconfiguration. The system monitors per-tile voltage, current and temperature via embedded sensors. It reallocates string groupings in software every 30 seconds to mitigate partial shading and thermal mismatch without hardware changes.

## Problem
Conventional solar panels achieve higher output per installed area than roof tiles because fixed string inverters cannot compensate for variable shading, debris accumulation and thermal gradients across curved tile surfaces. This leads to 15-25% lower annual energy yield, prompting discontinuation decisions.

## Prior art
- US10097005B2 Self-configuring photo-voltaic panels: describes hardware sockets and static configuration; this invention replaces static setup with runtime firmware string reallocation.
- US20180205343A1 Systems and methods for building-integrated power generation: covers integrated storage elements; this invention adds only firmware layers on existing tile microcontrollers.

## Summary of the invention
The invention provides a firmware module loaded into each tile's microcontroller that continuously recomputes optimal MPPT setpoints and virtual string boundaries using a lightweight gradient-descent algorithm. Reference numerals: tile microcontroller (12), voltage sensor (14), current sensor (16), temperature sensor (18), central gateway (20).

## Claims
1. A method for operating a photovoltaic roof tile array comprising: reading voltage, current and temperature from each tile at intervals of 30 seconds or less; executing a firmware algorithm that computes new virtual string groupings; and commanding DC-DC converters to reconfigure electrical connections within 2 seconds of each computation.
2. The method of claim 1 wherein the algorithm uses a gradient descent step size of 0.05 V per iteration and terminates after 12 iterations or when power change is less than 0.8 W.
3. The method of claim 1 further comprising storing a rolling 24-hour history of shading events in non-volatile memory of tile microcontroller (12) and using the history to pre-bias initial MPPT targets.
4. The method of claim 1 wherein the central gateway (20) broadcasts a common time base accurate to 50 ms to synchronize all tile microcontrollers (12).
5. The method of claim 1 further comprising detecting sensor failure when temperature reading deviates more than 12 °C from the median of neighboring tiles and substituting an estimated value derived from the prior 5 minutes of data.

## Brief description of the drawings
FIG. 1 shows a cross-section of three adjacent roof tiles with embedded sensors and firmware-controlled switches.

## Detailed description
Each roof tile contains a tile microcontroller (12) that samples voltage sensor (14) at 12-bit resolution every 500 ms. Current sensor (16) provides Hall-effect measurement accurate to ±1.5 %. Temperature sensor (18) is a thermistor with ±0.8 °C accuracy mounted on the rear aluminum heat spreader. The firmware maintains an internal model of expected irradiance based on time of day and roof azimuth. When measured power deviates more than 4 % from the model, the gradient-descent routine adjusts the target voltage of the local DC-DC converter. Virtual string boundaries are updated by opening or closing MOSFET switches rated 40 A continuous at 150 °C junction temperature. In case of communication loss with central gateway (20) for longer than 90 seconds, each tile microcontroller (12) reverts to a fixed 32 V MPPT setpoint. All numerical parameters are stored in flash memory and can be updated over the air. The algorithm requires 8 kB of RAM and executes in under 18 ms on a 48 MHz ARM Cortex-M0 core. Failure mode of a single failed sensor is handled by median filtering across the array; a failed microcontroller causes its tile to be isolated by opening its output switch within 800 ms. The complete firmware image is 124 kB and is verified by CRC-32 before execution. All dimensions and tolerances stated above are implemented directly in the firmware constants.