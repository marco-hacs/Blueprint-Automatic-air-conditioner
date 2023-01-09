# Automatic-air-conditioner

This blueprint is for using the air conditioner automatically in both winter and summer, based on a start and end temperature. In modo facoltativo, si può abilitare:

- Window status check 
- Water level control in the tank 
- Home presence control 
- Notifications (English and Italian)
- Decide on the time slot for operation

Below the settings for operation are:

1) **Select language**: Choose the language for notifications (default: Italian). 
2) **Entities climate**: Choose the climate entity to be used. 
3) **Select season**: Choose the season of use (default: Summer)
4) **Set temperature climate**: Select the temperature to be set at the climate 
5) **Hvac modes**: Select hvac usage mode (heat, cool, dry, fan\_only)
6) **Fan modes**: Select the fan usage mode (auto, high, mid, low). In case your climate settings are different from mine, these can be customized from the source file.
7) **Presence Home**: OPTIONAL Select from the list the group created with person entities for: 
- Turn on the air conditioner if the conditions set for startup are met
- Turn off the air conditioner at the time when you switch to the not\_home state
```
group:
  famiglia:
    entities:
      - person.marco
      - person.serena
```
8) **Water level**. OPTIONAL: Select the binary\_sensor used to indicate full water tank. To function, it must be set with *device\_class: moisture*.
9) **Window**: OPTIONAL select the binary sensor used for the window contact. To function, it must be set with *device\_class: window*
10) **Target temperature start**: Set the startup temperature:
- If set to winter, the climate will be turned on if the indoor temperature is lower than the set temperature
- If set to summer, the climate will be turned on if the indoor temperature is higher than the set temperature
11) **Target temperature stop**: Set the shutdown temperature:
- If set to winter, the climate will be turned off if the indoor temperature is higher than the set temperature
- If set to summer, the climate will be turned off if the indoor temperature is lower than the set temperature
12) **Delay temperature stop**: Set a delay expressed in minutes for turning off the air conditioner once it reaches “*Target temperature stop*”
13) **Start time**: Set the start time for automatic operation of the climate. NB: If you want the climate to be automatic h24, set Start time and Stop time with the time 00:00:00.
14) **Stop time**: Set the time for automatic climate operation end time and shutdown time. NB: If you want the climate to be automatic h24, set Start time and Stop time with the time 00:00:00.
15) **Device to notify push**: OPTIONAL select the device on which you want to receive the push notification. The device must have the official HomeAssistant app installed.

This blueprint was made respecting my personal needs and climate entities that are used with Broadlink. 

I remain open to feedback and any ideas to make this blueprint more usable for everyone.

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fmarco-hacs%2FAutomatic-air-conditioner%2Fblob%2Fmain%2Fautomatic_air_conditioner.yaml)
https://community.home-assistant.io/t/automatic-air-conditioner/511251
