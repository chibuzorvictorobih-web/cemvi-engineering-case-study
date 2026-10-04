# Sources — chilled-water calculation

1. U.S. Department of Energy. *DOE Fundamentals Handbook: Thermodynamics, Heat Transfer, and Fluid Flow*, Volume 2, Heat Exchangers, p. 36.
   https://www.energy.gov/documents/doe-hdbk-1012-92vol2

   Used for the heat-balance equation:
   heat-transfer rate = water mass flow × specific heat capacity × temperature change.

2. National Institute of Standards and Technology (NIST). *Fire Fighting Properties*, NISTIR 6191.
   https://doi.org/10.6028/NIST.IR.6191

   Used for water's approximate specific heat capacity of 4.186 kJ/(kg·K), rounded to 4.19 kJ/(kg·K) in this calculation.

The 7°C supply temperature and 12°C return temperature are invented project assumptions. The 33 kW peak comes from our invented cooling_demand.csv table. The 1.58 kg/s water flow is our calculated result.