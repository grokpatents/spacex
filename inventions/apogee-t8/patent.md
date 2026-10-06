# Overpressure Relief Valve for Rocket Engine Firewall Cavity

## Abstract
A passive overpressure relief valve assembly mounted in the engine firewall of a reusable rocket stage prevents excess pressure buildup in the cavity above the engines. The valve uses a spring-loaded poppet with a 25 mm diameter orifice, set to open at 35 kPa differential, venting to atmosphere through a heat-resistant duct. Materials are Inconel 718 for the body and poppet, with graphite seals rated to 800 °C. The design includes redundant sensors for monitoring and a fail-safe burst disk at 70 kPa.

## Problem
During initial burn of Ship 34 on flight test 8, four of six Raptor engines shut down early due to excess pressure in the cavity above the engine firewall. The pressure likely originated from a propellant system leak or thermal expansion, leading to loss of attitude control and vehicle breakup. Prior designs lacked automatic relief for this cavity during ascent.

## Prior art
- US20100096491A1, Rocket-powered entertainment vehicle: describes general rocket vehicle structures but no specific firewall cavity pressure relief for orbital stages.
- RU2557125C2, Aft body of aircraft with annular location of jet engine nozzles: covers heat reflectors in aft sections but does not address dynamic overpressure venting during engine operation.

## Summary of the invention
The invention is a spring-loaded poppet relief valve integrated into the engine firewall. It opens at a predetermined differential pressure to vent the cavity, preventing engine shutdowns from pressure-induced damage or sensor faults. The valve resets on pressure equalization and includes thermal protection and monitoring.

## Claims
1. A pressure relief valve for a rocket engine firewall comprising a valve body (12) mounted through an opening (14) in the firewall (16), a poppet (18) with diameter 25 mm biased by spring (20) having rate 120 N/mm to a closed position, wherein the poppet opens at a differential pressure of 35 kPa to vent cavity (22) above the firewall.
2. The valve of claim 1 further comprising a heat shield duct (24) of Inconel extending 150 mm aft of the firewall with wall thickness 1.5 mm.
3. The valve of claim 1 wherein the poppet (18) and body (12) are Inconel 718 and the seal (26) is graphite rated to 800 °C.
4. The valve of claim 1 further comprising a redundant pressure sensor (28) mounted in the cavity (22) and a burst disk (30) rated to 70 kPa.
5. The valve of claim 1 wherein the spring (20) is sized such that full open flow area is reached at 50 kPa differential with flow coefficient Cv greater than 8.
6. The valve of claim 4 wherein the sensor (28) signals a flight computer to log pressure data and trigger engine throttling if pressure exceeds 25 kPa for more than 200 ms.

## Brief description of the drawings
FIG. 1 shows a cross-section of the relief valve installed in the engine firewall with neighboring engine components.

## Detailed description
The engine firewall (16) is a 6 mm thick Inconel 718 plate separating the propellant tanks from the six Raptor engines. An opening (14) of 32 mm diameter is machined in the firewall at a location 400 mm from the nearest engine gimbal actuator. The valve body (12) is welded into this opening with a fillet weld of 3 mm leg length. The poppet (18) has a sealing face angled at 45 degrees and contacts the graphite seal (26) in the closed position. Spring (20) is a helical compression spring of 18 mm outside diameter made of Inconel X-750, preloaded to 85 N at installation. When cavity (22) pressure exceeds ambient by 35 kPa the poppet lifts 4 mm, providing a flow area of 310 mm². The heat shield duct (24) routes vented gas aft and is attached to the body (12) with six M4 bolts. Pressure sensor (28) is a piezoresistive transducer with 0-200 kPa range and 1 ms response time, mounted on a boss 50 mm from the valve centerline. Burst disk (30) is a scored Inconel membrane 0.3 mm thick that ruptures at 70 kPa to provide backup path. In normal operation the valve remains closed during static fire and initial ascent. If a propellant leak raises cavity pressure, the poppet opens within 50 ms, venting at up to 0.8 kg/s of helium or methane mixture. After pressure equalizes to within 5 kPa the spring reseats the poppet. Failure mode of spring fracture is mitigated by the burst disk. Thermal expansion of the poppet is accommodated by 0.2 mm radial clearance in the guide bore. All dimensions are held to ±0.1 mm tolerance except spring rate which is ±5 %. The valve adds 1.2 kg mass to the stage.