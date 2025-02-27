# Home assistant Custom component for Pax Calima

## Installation

Download using HACS or manually put it in custom_components folder.

## Add device

The integration supports discovery of devices, so any fans should be automatically discovered.
If not you may try to add it manually through the integration configuration.

## Sensor data

The sensors for temp/humidity/light seem to be a bit inaccurate, or I'm not converting them correctly, so don't expect them to be as accurate as from other dedicated sensors.
Humidity sensor will show 0 when humidity is low!
Air flow is just a conversion of the fan speed based on a linear correlation between those two. This is a bit inaccurate at best, as the true flow will vary greatly depending on how your fan is mounted.


## Good to know

Speed and duration for boostmode are local variables in home assistant, and as such will not influence boostmode from the app. These variables will also be reset to default if you re-add a device.

Configuration parameters are read only on Home Assistant startup, and subsequently once every day, to get any changes made from elsewhere.

Fast scan interval refers to the interval after a write has been made. This allows for quick feedback when the fan is controlled, and does not disconnect between reads. This fast interval will remain for 10 reads.

## Thanks

@PatrickE94 for the Calima driver:
https://github.com/PatrickE94/pycalima

@MarkoMarjamaa for a good starting point for the HA-implementation
https://github.com/MarkoMarjamaa/homeassistant-paxcalima
