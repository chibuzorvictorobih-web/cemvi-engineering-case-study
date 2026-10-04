# CEMVI: Cooling, Energy, Materials and Vibration Integration

**An independent educational project by Chibuzor Victor Obih**

CEMVI studies a **fully fictional equipment room**. Imaginary equipment and sunlight add heat to the room. An air-handling unit (AHU) moves room air across a chilled-water coil. An illustrative air-cooled chiller, described conceptually with R-513A refrigerant, removes heat from the returning water and rejects it outdoors.

The project uses invented operating inputs and publicly sourced engineering relationships. It contains no employer data or measurements from an operating installation.

## Project question

How does a changing hourly room cooling load affect calculated cooling-system electricity and direct solar-PV use? How do assumed material properties, support dimensions, and repeated forces affect a simplified support-arm comparison? Which results change when the assumptions change?

## Model and scope

The notebooks calculate:

1. A fictional 24-hour cooling load from two equipment heat inputs and sunlight heat entering the room.
2. Cooling-system electricity under alternative constant chiller COP assumptions. The model includes an AHU fan and chilled-water pump.
3. Hourly matching of an invented PV electricity profile to cooling-system demand. The main comparison uses direct PV and grid supply without a battery; the cooling-demand notebook also contains a separate simplified storage example.
4. Mass, stiffness, and static tip deflection for idealised steel and aluminium support arms.
5. A simplified, single-direction steady-state vibration response to an invented repeated force.
6. One-at-a-time sensitivity tests for room heat, COP, PV supply, support inputs, and vibration inputs.

The central calculation relationships are:

- Hourly room heat load = equipment A heat + equipment B heat + sunlight heat.
- Hourly cooling-system electrical power = room cooling load ÷ assumed chiller COP + AHU fan power + chilled-water pump power.
- Direct PV use each hour = the smaller of PV electrical supply and cooling-system electrical demand.

The R-513A chiller describes the **conceptual system arrangement**. This project does not calculate refrigerant properties or simulate a detailed refrigeration cycle.

## Project files

| Path | Contents |
|---|---|
| `data/cooling_demand.csv` | Invented hourly equipment heat, sunlight heat, and total cooling load |
| `data/pv_supply.csv` | Invented hourly PV electrical supply |
| `notebooks/01_cooling_demand.ipynb` | Cooling load, illustrative electricity, PV, and related calculations |
| `notebooks/02_material_support.ipynb` | Idealised support-arm material comparison |
| `notebooks/03_vibration_model.ipynb` | Simplified vibration comparison and mathematical checks |
| `notebooks/04_sensitivity.ipynb` | One-at-a-time sensitivity comparisons |
| `figures/` | Graphs produced by the notebooks |
| `assumptions.md/` | Files identifying invented inputs and model boundaries |
| `sources.md/` | Files recording public sources for borrowed equations and material properties |

## How to run the project

1. Open the complete CEMVI project folder in VS Code.
2. Select the Python environment used for the project, with Jupyter and Matplotlib available.
3. Open each notebook in this order: `01_cooling_demand.ipynb` → `02_material_support.ipynb` → `03_vibration_model.ipynb` → `04_sensitivity.ipynb`.
4. For each notebook, restart its kernel and run all cells from the top. Save the notebook after it finishes.
5. Check the printed values and graphs. The notebooks read the CSV files from `data/` and save figures in `figures/`.

The four notebooks were run from fresh kernels during the project check. Both CSV files contained 24 matching hourly labels, and the file audit found the figures.

## Illustrative results

| Comparison | Result for the invented case |
|---|---|
| Heat removed over the fictional day | 547.00 kWh thermal |
| Cooling-system electricity at COP 3.0 and COP 4.0 | 225.53 and 179.95 kWh electrical/day, respectively |
| Invented PV supply in the COP 3.0 case | 101.00 kWh electrical produced; 84.20 kWh used directly; 16.80 kWh unused directly |
| Grid supply in the COP 3.0, no-battery case | 141.33 kWh electrical/day |
| Idealised support arm under a 100 N static tip force | Steel: 1.185 kg and 1.080 mm tip deflection; aluminium: 0.405 kg and 3.130 mm |
| Simplified movement at an invented 5 N, 10 Hz repeated force and damping ratio of 0.10 | Steel: approximately 0.092 mm; aluminium: approximately 0.483 mm steady-state amplitude |

The fan and pump together account for an assumed constant **1.8 kW** of the cooling-system power. The outdoor condenser fan is included within the assumed chiller-package COP.

## What the sensitivity tests show

- In the invented daily profile, a ±20% change in equipment heat affects total cooling demand more than a ±20% change in sunlight heat.
- Higher assumed chiller COP reduces calculated electricity for the same cooling duty, while the size of the difference depends on the chosen COP values.
- Increasing invented PV output reduces calculated grid use, but some PV remains unused when its supply exceeds cooling demand in the same hour. Moving the PV profile by one hour changes direct use even when daily PV production stays at 101 kWh.
- The idealised arm's vertical thickness has a strong effect on calculated deflection. The vibration result also depends on the assumed frequency, force, and damping.

## Limits and evidence

All room heat inputs, schedules, fan and pump powers, COP values, PV supply, arm geometry, attached mass, repeated force, and damping assumptions are illustrative. Material properties and engineering equations are traced to public sources in `sources.md/`. Invented inputs and boundaries are recorded in `assumptions.md/`.

The model assumes constant COP across the day, uses simplified hourly PV matching, treats the support as an idealised cantilever, and represents vibration with one steady-state motion. It does not establish real electricity savings, real PV production, refrigerant performance, a safe component design, or vibration of an operating machine.

This project was developed independently and contains no employer drawings, equipment tags, operating measurements, or private workplace data.

[Read the findings and limitations](notes/findings_and_limitations.md)

Install the plotting package with `python -m pip install matplotlib`.