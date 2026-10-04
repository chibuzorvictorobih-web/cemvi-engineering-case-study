# CEMVI sensitivity assumptions
## Room heat inputs
- Baseline: the 24 invented hourly rows in data/cooling_demand.csv.
- Equipment scenarios: multiply equipment A and B heat by 0.8 or 1.2; keep sunlight heat at baseline.
- Sunlight scenarios: multiply solar heat entering the room by 0.8 or 1.2; keep equipment heat at baseline.
- These 20% changes are invented tests, not uncertainty measured from real equipment.
- Each hourly value is an average over one hour. Summed daily heat uses kWh thermal.
- The baseline CSV is not edited.
## Efficiency sensitivity
- Original comparison: invented baseline COP 3.0 and improved COP 4.0.
- Baseline COP tests: 2.5, 3.0, and 3.5 while improved COP remains 4.0.
- Improved COP tests: 3.5, 4.0, and 4.5 while baseline COP remains 3.0.
- The original 24-hour cooling profile stays fixed.
- AHU fan power remains 1.2 kW and chilled-water pump power remains 0.6 kW for all 24 hours.
- The outdoor condenser fan is counted within the assumed chiller-package COP; it is not added again.
- COP is treated as constant across the day. All tested COP values are illustrative, not measured performance.
## PV sensitivity
- Source profile: the invented 24-hour electrical PV profile in data/pv_supply.csv, producing 101 kWh over the day.
- Size tests: multiply each hourly PV value by 0.75 or 1.25.
- Timing tests: shift the original values one hour earlier or later without changing the 101 kWh daily total.
- Cooling-system demand stays at COP 3.0 plus 1.2 kW AHU fan and 0.6 kW chilled-water pump.
- Direct PV use, grid supply, and unused PV are calculated hour by hour without battery storage.
- Sunlight heat entering the room is held fixed. The PV shifts are invented mathematical tests, not a coupled weather model.
## Support-arm sensitivity
- Original geometry: length 300 mm, width 50 mm, vertical thickness 10 mm.
- Original static tip force: 100 N.
- Change Young's modulus by ±10% with geometry and density fixed.
- Separately change vertical thickness by ±10% with Young's modulus and density fixed.
- The ±10% values are invented sensitivity tests, not stated material tolerances.
- For natural frequency, retain the same fictional 10 kg attached moving mass and omit the arm's distributed moving mass.
- Material values and beam equations remain documented in the source logs.
## Vibration sensitivity
- Original inputs: 10 kg attached moving mass, 10 Hz repeated-force frequency, 5 N force amplitude, and 0.10 damping ratio.
- Original support stiffness: 92,592.59 N/m for steel and 31,944.44 N/m for aluminium.
- Force test: use 3.75 N, 5.00 N, and 6.25 N with damping ratio fixed at 0.10.
- Damping test: use ratios 0.05, 0.10, and 0.20 with force amplitude fixed at 5.00 N.
- Only one input changes in each test. Geometry, stiffness, moving mass, and push frequency stay fixed.
- Each arm uses the stated damping ratio to calculate its own damping coefficient from its stiffness and the 10 kg mass.
- The alternative force and damping values are invented sensitivity tests, not measured operating conditions.