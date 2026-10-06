# Redundant Torch Igniter Assembly for Liquid Rocket Engines

## Abstract
A redundant torch igniter assembly for a liquid rocket engine such as the Raptor uses two independent spark torches fed from separate propellant taps and electrical circuits. The assembly mounts on the injector dome and provides ignition energy to the main chamber even if one torch fails to light or its spark plug fouls. Sensors monitor chamber pressure in each torch and switchover logic commands the second torch within 50 ms of detected failure.

## Problem
During boostback relight of Super Heavy, one center Raptor engine aborted ignition because its single torch igniter failed to establish a stable flame kernel. The engine controller detected insufficient chamber pressure rise and shut down the engine, reducing thrust margin for the return trajectory.

## Prior art
- EP4030046B1 Multi-time ignition starting apparatus for a rocket engine: uses a single gas generator torch with sequenced valves; this invention adds a fully independent second torch with separate electrical and propellant paths.

## Summary of the invention
The invention places two torch chambers (12, 14) side-by-side on the injector face. Each torch receives methane and oxygen from dedicated orifices (16, 18) sized for 3 g/s total flow at 20 bar. Separate high-voltage leads (20, 22) connect to redundant exciters. A pressure transducer (24) in each torch reports to the engine controller. On command the controller energizes both exciters; if torch A pressure does not exceed 8 bar within 80 ms, torch B remains lit and its output is used alone.

## Claims
1. A redundant igniter assembly for a liquid rocket engine comprising two independent torch chambers each having its own propellant inlets, spark plug, and pressure sensor, mounted on the injector dome and controlled by logic that activates the second torch upon failure of the first.
2. The assembly of claim 1 wherein each torch chamber has a volume between 8 cm³ and 12 cm³ and an aspect ratio of 3:1.
3. The assembly of claim 1 further comprising separate high-voltage exciters powered from independent 28 VDC buses.
4. The assembly of claim 1 wherein the propellant orifices are sized to deliver a mixture ratio of 2.8:1 at a total mass flow of 3 g/s per torch.
5. The assembly of claim 1 wherein the controller declares failure when torch chamber pressure remains below 8 bar for more than 50 ms after spark command.
6. The assembly of claim 1 wherein the torch outlets are angled 30 degrees toward the main injector orifices to ensure flame propagation into the main chamber.

## Brief description of the drawings
FIG. 1 shows a cross-section of the dual torch igniter mounted on the injector dome.
FIG. 2 shows the electrical and propellant schematic with sensor and valve placement.

## Detailed description
The injector dome (30) carries two cylindrical torch bodies (12, 14) machined from Inconel 718. Each body contains a spark plug (32) rated 20 kV, a methane inlet orifice (16) of 0.8 mm diameter, and an oxygen inlet orifice (18) of 0.5 mm diameter. Propellant is tapped from the main valve manifolds upstream of the main injectors so that torch flow is available at the same time as main propellant arrival. A 0-50 bar piezoresistive transducer (24) threads into each torch body and supplies 4-20 mA to the engine controller. The two torches are spaced 45 mm apart on centers. Their outlets (34) are drilled at 30 degrees to the dome axis. On ignition command both exciters receive 28 VDC. If transducer (24) in torch A does not register 8 bar within 80 ms, the controller latches torch A off and confirms torch B pressure above 8 bar before enabling main propellant valves. Failure modes addressed include spark plug fouling, blocked orifice, and exciter open circuit; each is detected by the pressure sensor and handled by the second torch. Tolerances on orifice diameters are held to ±0.02 mm to maintain mixture ratio within ±5 %. The assembly adds 1.2 kg to engine mass and requires two additional electrical connectors.