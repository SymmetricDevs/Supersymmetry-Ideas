---
tags:
  - Concept-Phase
  - Oreverhaul
  - Overhauls
---
In the current state, the big ore drill provides a big stream of free^[aside from power] resources, some of which are either orphaned (single use case) or entirely worthless and unused. 

The usability and „Junk“ acquired has been addressed in [Issue \#967](https://github.com/SymmetricDevs/Supersymmetry/issues/967) and the related [PR](https://github.com/SymmetricDevs/Supersymmetry/pull/972). 
It also is so strong and easy to use that conventional mining (may it be automatic or manual) becomes obsolete entirely. I‘ll address this as well in a separate file.
# Extract
To add some amount of challenge and expenses to operating this drill, I propose these factors:
- Lubrication (Drilling Fluid)
- Cooling
- Gangue/Deaf Rock 
- *Drilling Fluid or Solvent* 
	- Only applicable to higher tiers which cannot be dug/bored easily. 
	- Probably reserved to exotic or extraterrestrial minerals. 
All of these are intended to be compounding but required for higher-tier usage (or failure/debuffs will ensue). 
This proposal also aims to provide upgrades that could push it to the capacities of higher tiers without using more power directly. 
I did consider using mining pipes but it is not sensical, given that the drill head never moves vertically. 
# A qualitative table
> [!NOTE] Note
> I always assume that people will overclock their multiblock whenever possible so this table reflects that. 
> Second, designing mechanics that are difficult initially but get tangibly easier with progression are very satisfying. 

| Tier/Power    | Base Speed | Avg. Rocks/s | Gangue % | Lubrication | Cooling  | Drilling Fluid/Solvent |
| ------------- | ---------- | ------------ | -------- | ----------- | -------- | ---------------------- |
| LV (32EU/t)   | 0.25       | 2-4          | 95%      | ❌ (+1✅)     | ❌(+1x✅)  | ❌                      |
| MV (128EU/t)  | 1          | 4-8          | 75%      | ❌(+2✅)      | ❌(1.5x✅) | ❌                      |
| HV (512EU/t)  | 4          | 4-12         | 50%      | ✅ (-2❌)     | ❌(+2x✅)  | ❌                      |
| EV (2048EU/t) | 8          | 8-16         | 25%      | ✅(-4❌)      | ✅(0.5x❌) | ✅                      |
# Supplied Upgrades
## Lubrication
Lubricant is the usual deal, behaving like LSTs. It would increase base machine speed with the lube consumption being dependent on the grade of lube used. 
It‘s not too complex, hopefully. 
## Cooling 
At higher speeds and imagined torques, the drill bit would heat up significantly, which would cause severe stress and wear on the system if unmitigated. 
Cooling could happen in three ways:
- Supply cold coolant (static fluid with a temp value of 273.15°K)/liquified gas
	- Returns Warm coolant (373.15°K)/gas-gas
	- This would likely require an on-site coolant/refrigeration cycle. 
- Quench/heat exchange a Hot Drill Head item
	- Returns a regular drill head which would be required for higher-speed ops. 
	- Using a drill head for speed boost and not cooling it has a 5% chance to break it. 
	- This would likely be an own set of two items since respecting both diamond and Tungcarbide would be bloating. 
- Internal “Temperature Value” tracking
	- This would be the best solution, but presumably the most complex to implement. Creating a method for having a floating value control a machine would also be hugely beneficial elsewhere (Smelting, Cryogenics, Distillation)
	- This value would resemble Nr.1 but less convoluted. 
	- Gameification could even allow extraction of power from this waste heat. 
### Drilling Fluid and Solvent 
All of the previous upgrades are generic, i.e. they do not tie to the material excavated. 
I wish to propose, if possible to implement, enabling a drilling fluid or solvent for harder or exotic deposits found on rare locations or outside of earth. 
This might find application for very hard or old formations.
# Speed Calculation 
TBD
# Gangue
TBD
