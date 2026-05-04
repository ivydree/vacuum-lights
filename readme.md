# 🧹 Smart Vacuum & Light Sync 💡

## 📖 Overview
This Home Assistant automation synchronizes your home lights with the movements of your robot vacuum.  
It automatically turns on the light in the room where the vacuum is cleaning or entering, and switches it off when the vacuum leaves or stops.

## ✨ Features
- 🔦 Lights turn on when the vacuum starts cleaning.
- 🚪 Lights turn on when the vacuum enters a room.
- 🚪 Lights turn off when the vacuum leaves a room.
- ⏸️ Lights turn off when the vacuum is paused, docked, idle, or in an error state.
- 🌞 Optional ambient light sensor with lux threshold.
- 👥 Optional presence detection (prevents lights from switching when someone is home).
- 💡 Optional adjustable brightness level for lights.

## ⚙️ Requirements

### Mandatory
- A working Home Assistant setup.
- A robot vacuum that exposes a **current room sensor** (e.g., Dreame L40s Pro Ultra with `sensor.current_room`).
- Light entities (`light.xxx`) mapped to your rooms.

### Optional
- Presence entities (`person.xxx`) to prevent lights from switching if someone is home.
- An ambient light sensor (`sensor.xxx`) with a lux threshold to avoid turning lights on when it’s already bright.
- Adjustable brightness level for lights when turning them on.

## 📥 Import Blueprint
##[![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FHoM3r17%2Fvacuum-lights%2Frefs%2Fheads%2Fmain%2Fsmart-vacuum-lights-sync)


## 🛠️ Setup
1. Copy the blueprint YAML file into your `blueprints/automation/` folder. *(Only needed if the import button above cannot be used.)*
2. Restart Home Assistant or reload automations. *(Only needed if the import button above cannot be used.)*
3. Create a new automation using this blueprint.
4. Fill in the inputs:
   - Vacuum entity.
   - Room sensor.
   - JSON mapping of rooms → lights.
   - (Optional) Presence entities, light sensor, brightness level.

## 📋 Example JSON mapping of rooms → lights

```
  {
    "Bathroom": "light.lumieres_sdb",
    "Dining Hall": "light.lumieres_sam",
    "Living Room": "light.lumieres_salon",
    "Kitchen": "light.lumieres_cuisine"
  }
```
