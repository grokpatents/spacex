# Redundant Propellant Isolation and Attitude Control System for Spacecraft Coast Phase

## Abstract
A spacecraft propellant system incorporates dual redundant isolation valves per tank line, each with integrated pressure transducers and flow sensors. Upon detection of sudden pressure drop exceeding 5 psi/s, flight computers isolate the affected line and switch to backup attitude control thrusters fed from a secondary manifold. The system maintains attitude control for at least 30 minutes post-leak using residual propellant, enabling controlled reentry or payload deployment. Materials include Inconel 718 valves rated to 3000 psi with 0.01 inch tolerance seats. Failure modes such as valve stuck-open are mitigated by series-parallel valve arrangement.

## Problem
During coast phase after main engine cutoff, a propellant leak causes rapid tank pressure loss. Flight computers initiate safing but lose attitude control authority because primary reaction control system (RCS) propellant is lost through the leak path. This prevents controlled reentry and aborts payload operations. Sudden pressure drops of 20-50 psi within seconds have been observed, overwhelming single-point isolation.

## Prior art
- US12012233B2, Active on orbit fluid propellant management and refueling systems and methods, describes propellant pumps and transfer but lacks automated leak isolation valves triggered by rate-of-pressure-change.
- US8056863B2, Unified attitude control for spacecraft transfer orbit operations, provides spin-stabilized attitude methods but does not address loss of propellant feed to RCS during leaks.

## Summary of the invention
The invention adds a leak detection module using differential pressure sensors (14) across each isolation valve (12). Valves are arranged in series-parallel pairs per feed line. On leak detection, the affected branch isolates in under 200 ms while a cross-feed valve (18) routes remaining propellant to a dedicated RCS manifold (22). Backup cold-gas or hypergolic thrusters (24) provide three-axis control using residual ullage pressure. Sensors sample at 100 Hz with triple modular redundancy.

## Claims
1. A spacecraft propellant system comprising: a main tank (10); a primary feed line (11); at least two series isolation valves (12a, 12b) in the primary feed line; a pressure rate sensor (14) coupled to the line between the valves; a controller (16) configured to close both valves when pressure decrease exceeds 5 psi per second; a secondary manifold (22) connected via cross-feed valve (18); and at least four RCS thrusters (24) supplied exclusively from the secondary manifold.
2. The system of claim 1, wherein each isolation valve is an Inconel 718 poppet valve with seat tolerance of 0.005 inch and response time under 150 ms.
3. The system of claim 1, further comprising triple-redundant pressure transducers (14) with 100 Hz sampling and majority voting logic in the controller.
4. The system of claim 1, wherein the cross-feed valve (18) opens only after primary isolation is confirmed by downstream pressure below 10 psi.
5. The system of claim 1, wherein the RCS thrusters (24) are sized to provide 0.5 deg/s^2 angular acceleration using residual propellant for a minimum of 1800 seconds.
6. The system of claim 1, further comprising a failure mode handler that commands a safe attitude hold using only surviving thrusters if one RCS branch fails post-isolation.

## Brief description of the drawings
FIG. 1 shows the propellant feed architecture with isolation valves and sensors.
FIG. 2 shows the RCS manifold and thruster arrangement with cross-feed.

## Detailed description
Main propellant tank (10) supplies oxidizer or fuel through primary feed line (11). Series isolation valves (12a) and (12b) are spaced 6 inches apart. Pressure rate sensor (14) measures dP/dt between the valves. Controller (16) executes the isolation logic: if dP/dt < -5 psi/s for two consecutive 10 ms samples, both valves close. Cross-feed valve (18) then opens to route remaining propellant from the isolated segment into secondary manifold (22). Manifold (22) supplies four RCS thrusters (24) arranged in opposing pairs for pitch, yaw, and roll. Each thruster (24) has a 0.25 inch orifice and operates on residual ullage gas or hypergolic residuals. Materials: all wetted parts Inconel 718, seals perfluorocarbon rated to -150 C. In case of valve (12a) stuck open, valve (12b) provides single-point isolation. Downstream pressure below 10 psi confirms isolation before cross-feed activation. The system tolerates one complete branch failure while retaining 75% attitude authority. Sensors are potted in epoxy for vibration resistance up to 20 g RMS. Total added mass is 28 kg.