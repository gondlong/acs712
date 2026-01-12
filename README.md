# ACS712 sensor component for esphome

This is based on https://github.com/RobTillaart/ACS712 and https://github.com/marianomd/acs712-esphome

The code is working on ESP32 and ACS712-20A.

Have in mind that without voltage divider will measure just up to 20A.

Example yaml fragment:

```
esphome:
  name: power-measure

external_components:
  - source:
      type: git
      url: https://github.com/gondlong/acs712
    components: [acs712]

sensor:
  - platform: acs712
    pin: 34
    voltage: 3.3
    adc_bits: 4096
    mv_per_amp: 100
    line_voltage: 220
    noisemV: 43
    current_sensor:
      name: "current"
    power_sensor:
      name: "power"


```
