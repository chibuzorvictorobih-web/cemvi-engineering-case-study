# CEMVI vibration-model assumptions
- The fan-and-motor module and its movement are fictional.
- Only one up-and-down movement at the free end of the arm is modelled.
- The arm is represented by its calculated tip stiffness.
- The same invented 10 kg moving-module mass is used for both material cases.
- The arm's own distributed mass, its fasteners, and other ways it could bend are omitted.
- Damping and the repeated force use the illustrative values listed below.
- The chosen static 100 N force is not the repeated vibration force.
- No real equipment or employer information is used.

## Invented numerical inputs

- Moving module mass: 10 kg, identical in both comparisons.
- Damping ratio: 0.10 in both comparisons. The corresponding damping coefficient is calculated separately for each arm.
- Repeated-push frequency: 10 Hz. It is illustrative, not an actual fan speed.
- Peak repeated-push amplitude: 5 N at the fictional peak cooling load of 33 kW.
- At each hour, push amplitude is assumed to equal 5 × (hourly cooling load / 33) N.
- Each hourly cooling load is treated as constant during that hour; the repeated push changes on a much faster, seconds-long timescale.
- The link between cooling load and push amplitude is invented. It does not predict real equipment vibration.
- For the frequency comparison, I hold force amplitude at an invented 5 N while varying frequency from 0.5 to 25 Hz. Both arms use the same assumed mass and damping ratio, but their calculated damping coefficients differ because their stiffnesses differ.