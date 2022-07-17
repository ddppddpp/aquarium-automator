# Light Automation #
Start by creating a light schedule using the Home Assistant Times of Day helper as shown in [light schedule](light_schedule.md), then create a basic 'turn on' automaiton using the GUI or yaml:

```
alias: Aquarium Light - Turn On
description: ''
trigger:
  - platform: state
    entity_id:
      - binary_sensor.aquarium_light_schedule
    to: 'on'
condition: []
action:
  - service: light.turn_on
    data: {}
    target:
      device_id: <<< put your device uuid or name here >>>
mode: single
```

Then add a 'turn off' automation:

```
alias: Aquarium Light - Turn Off
description: ''
trigger:
  - platform: state
    entity_id:
      - binary_sensor.aquarium_light_schedule
    to: 'off'
condition: []
action:
  - service: light.turn_off
    data: {}
    target:
      device_id: <<< put your device uuid or name here >>>
mode: single

```

Note that both automations refer to the Light Schedule helper.
