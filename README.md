# PurpleAir Lite Home Assistant Integration

A custom copy of the Home Assistant Core PurpleAir integration which limits the number of sensors queried.

## Why?

PurpleAir charges for their API, the current integration in homeassistant core does not query PurpleAir efficiently.
[HACore issue 146600](https://github.com/home-assistant/core/issues/146600)


## Warning - In progress

This is not ready for prime time yet, but it works for my specific use case.
Drops number of PurpleAir API points used per call from 41 to 11:
Only pulls data for Temp, Humidity, and VOCs

If I get time, I will make it configurable, save and lookup which HA sensors are disabled any query only for the ones that are enabled.
Right now to change which sensors are updated you would need to fork this repo and edit the list in coordinator.py
(2025-06-14)


## Installation with HACS

[![Type](https://img.shields.io/badge/Type-Custom_Component-orange.svg)](https://github.com/dlarrick/hass-kumo) [![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

The simplest way to install this integration is with the Home Assistant Community Store (HACS). This is not (yet) part of the default store and will need to be added as a custom repository.

Setting up a custom repository is done by:

1. Go into HACS from the side bar.
2. Click into Integrations.
3. Click the 3-dot menu in the top right and select `Custom repositories`
4. In the UI that opens, copy and paste the [url for this github repo](https://github.com/Jasonbluefire/ha-cc-purpleair_lite) into the `Add custom repository URL` field.
5. Set the category to `Integration`.
6. Click the `Add` button.
7. Select PurpleAir Lite from the list and press the download button. 
8. Further configuration is done within the Integrations configuration in Home Assistant. You may need to restart home assistant and clear your browser cache before it appears, try ctrl+shift+r if you don't see it in the configuration list.


## Configuration

Get a PurpleAir API key:

1. Create an account, or log into your account: https://develop.purpleair.com/
2. Create or find your project.
3. Create or get your API Key.

Setup the HA Integration:

1. Settings > Devices > Add Integration > PurpleAir_Lite
2. Paste API Key
3. Find and select the PurpleAir sensor your want
4. Go back into the Integration once its set up and disable the HA sensors that are not updated/used