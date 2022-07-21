# Temperature Notifications #


Use the following example to build an automation that sends an alert if the temperature, reported by the DS18B20 is outisde of set limits.

The trigger is the event of temperature change above or below the chosen limit for a period of 5 minutes (to avoid false alarms).
The action is a notification sent to a mobile app.
The current Home Assiant GUI (2022.7) doesn't support templates in the notification message body, so you'll have to use the YAML editor or default to a plain text message.



```
alias: Notify on Aquarium Temperature Out of Safe Limits
description: ''
trigger:
  - platform: numeric_state
    entity_id: sensor.aquarium_water_temperature
    for:
      hours: 0
      minutes: 5
      seconds: 0
    below: '23'
  - platform: numeric_state
    entity_id: sensor.aquarium_water_temperature
    for:
      hours: 0
      minutes: 5
      seconds: 0
    above: '28'
condition: []
action:
  - service: notify.mobile_app_iphone
    data:
      message: >
        The current aquarium water temperature is {% set state =
        states('sensor.aquarium_water_temperature') %} {%if is_number(state) and
        state | float > 28 %}
          too warm.
        {% elif is_number(state) and state | float < 23 %}
          too hot.
        {% else%}
         {{ states('sensor.aquarium_water_temperature') }}
        {% endif %}
mode: single
```
