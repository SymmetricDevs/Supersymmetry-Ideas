---
tags:
  - Aerospace
  - Concept-Phase
---
# Overview
Modules are the components that make up a [Rocket](Rocket.md). Each rocket is constructed from various modules that the player assembles as a multiblock. 
Modules are categorized into **required** and **optional**, and they stack vertically. Each module is defined in a JSON file containing its structure and attributes (details at the end of the file).

---

## 1. Module General Information

- A rocket can have X required modules and Y optional modules. The [launchpad](Launchpad.md) and engines determine how many custom modules can be placed.
- **All** modules have fixed exteriors, but some allow customization within, providing flexibility for specialization.
- Module size is limited by the launchpad size.
### Key Advantages:
- **Specialization**: Rockets can be customized based on the selected modules.
- **Progression**: Rockets evolve with tier advancement and available resources.
- **Flexibility**: Developers can modify modules by editing a JSON file without changing the core rocket logic.
- **Expandability**: New modules can be added by simply introducing new JSON files.
## 2. Required Modules

Required modules are the ones that are required :)

Examples include:
- Engine Module
- Fuel Storage Module
- Cockpit Module
- Navigation Module

Each required module type must be present for a rocket to be assembled. This system supports having different variants for each tier, giving players aesthetic and functional options.
These modules feature **fixed exteriors and interiors**, though developers can allow players to add blocks in empty spaces if desired.
## 3. Optional/Custom Modules

Optional/Custom modules enable rocket customization. For example:
- Want a cargo module? Add one.
- Want to transport your skeletal horse from 2023 SuSy into space? No problem!
These modules provide flexibility, letting players place almost any block, though restrictions on accepted block types can be enforced by devs. Module exteriors are fixed though.
Custom modules were conceived to allow people a puzzle solution for transporting goods, machinery and whatnot without an arbitrary slot limit of "you can only fit five items into this compartment.".

---

## 4. JSON File Structure

Each module is represented in a JSON file, with the following common structure:

- **id**: A unique identifier for each module.
- **type**: The type of module (e.g., engine, custom, command_module).
- **required**: `true/false` indicating whether the module type is required.
- **can_edit**: `true/false` indicating whether the player can modify empty spaces within the module.
- **repeatable**: A number, indicating the amount of modules of this ID you can place (0 to be infinite).
- **structure**: A 3D vector representing the multiblock for structure integrity validation at assembly. Think of it like a floor plan for each layer.

### Example JSON File:

```json
{
    "id": 1,
    "type": "random_box",
    "tier": 1,
    "required": true,
    "can_edit": false,
    "repeatable": 2,
    "structure": [
        [
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"],
            ["X", "X", "O", "X", "X"],
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"]
        ],
        [
            ["X", "X", "X", "X", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "X", "X", "X", "X"]
        ],
        [
            ["X", "X", "X", "X", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "0", "0", "0", "X"],
            ["X", "X", "X", "X", "X"]
        ],
        [
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"],
            ["X", "X", "X", "X", "X"]
        ]
    ]
}
```
The example shows a 5x5x4 box with a hole in the center of the top layer.

## 5. Other ideas

- Instead of having a fixed amount of modules per launchpad/engine tier, they can provide a max rocket weight. Each JSON can now have a `weight` parameter and the total weight is checked on assembly. Nevertheless, required modules would still be required.
	(This was sourced from a contribution by @divine-ray as they criticised hard gating of rockets to be uncreative.)