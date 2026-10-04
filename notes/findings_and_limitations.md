# CEMVI — Findings and limitations

## What this project explored

CEMVI is an educational model of a fictional equipment room cooled by an air-cooled chiller. I used invented hourly heat loads to compare cooling electricity, an illustrative solar PV supply, two materials for a support arm, and the arm’s response to a changing force. The results describe this model only.

## Main findings

1. **Cooling demand changes through the day.** The room’s modelled heat load peaks at 33 kW at 12:00. Over 24 one-hour periods, the chiller must remove 547 kWh of heat.

2. **Chiller efficiency affects electricity use.** With an assumed cooling COP of 3, the model uses 225.53 kWh of electricity per day, including the assumed fan and pump electricity. At COP 4, it uses 179.95 kWh per day. The difference is 45.58 kWh per day, approximately 20.21% of the baseline electricity use.

3. **Solar electricity helps when its timing matches demand.** The invented PV profile produces 101.00 kWh in a day. Without battery storage, 84.20 kWh is used directly, 16.80 kWh is unused, and the grid supplies 141.33 kWh of the baseline electricity demand.

4. **Material choice involves more than weight.** For the same fictional support-arm shape and 100 N tip force, the steel arm has a calculated mass of 1.185 kg and tip deflection of 1.08 mm. The aluminium arm has a calculated mass of 0.405 kg and tip deflection of 3.13 mm. Aluminium is lighter in this comparison, while steel is stiffer.

5. **The vibration comparison depends on the chosen inputs.** With the invented 10 kg attached mass, 10 Hz forcing, and damping ratio of 0.10, the calculated noon vibration amplitude is about 0.092 mm for steel and 0.483 mm for aluminium. These values describe the simplified model and its assumed operating point.

6. **Input choices affect the conclusions.** Changing the invented equipment heat inputs by ±20% changes the daily heat total from 547 kWh to 446 or 648 kWh. Changing the invented solar heat input by ±20% changes it to 538.6 or 555.4 kWh. In these particular scenarios, the equipment inputs have the larger effect.

## Limits of the model

- The equipment loads, sunlight, PV production, component sizes, operating schedules, and several efficiency values are invented. They are recorded as assumptions, not measurements.
- Each hourly load represents a one-hour average. Short changes within an hour are outside this model.
- A fixed COP represents chiller performance. The notebook does not simulate the detailed R-513A refrigerant cycle or changing chiller performance with outdoor temperature.
- The PV comparison uses one invented day. Actual solar output varies with weather and location.
- The support arm is treated as a simple fixed-end beam. The static calculation leaves out the arm’s own weight, joints, and mounting details.
- The vibration calculation uses an idealised mass, damping ratio, and periodic force. It is an educational response comparison.
- These results are suitable for explaining engineering trade-offs in a fictional case. They are not equipment specifications or a design for installation.

Public sources for borrowed equations and properties are recorded in the project's source records. Invented inputs are identified in the assumptions records.