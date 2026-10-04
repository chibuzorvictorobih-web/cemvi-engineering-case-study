# Fictional battery assumptions
- This battery case uses the same baseline cooling-system electricity demand as used earlier on: chiller COP 3.0, AHU fan 1.2 kW, and chilled-water pump 0.6 kW. The hourly cooling demand does not change.
- Each time step lasts one hour.
- The battery can hold a maximum of 12 kWh of stored energy. It starts the day empty (0 kWh).
- Charging efficiency is assumed to be 90%: when 1 kWh of extra PV electricity enters the battery, 0.90 kWh is stored.
- Discharging efficiency is assumed to be 90%: removing 1 kWh from the battery provides 0.90 kWh to the cooling system. The combined charge-and-discharge efficiency is 81%.
- In each hour, PV electricity serves the cooling system first. Any extra PV charges the battery until it is full; remaining PV is unused.
- When PV is insufficient, the battery supplies as much as its stored energy allows. The grid supplies the remaining demand.
- The battery never charges from the grid, and electricity is not exported.
- Charging and discharging power limits, self-discharge, battery ageing, and costs are omitted from this simple model.
- The capacity, efficiencies, and operating rules are invented for education. They are not specifications or measured performance for a real battery.
Matching uses one-hour average PV and demand values; changes within each hour are omitted.