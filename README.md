# aquarium-automator
A device that helps monitor and automate basic aquarium/ fish tank needs


- Monitor
  - Temperature
  - Water quality (ph?)
- Automations
- relay triggering
- thermostat
- light schedule
  - fixed schedule
- Various reminders for chores, i.e.
  - Feeding
  - Water Cleaning/ Maintenance
  
### Platform ###
- ESP8266 for sensor data and relay trigger
- HomeAssistant for schedule orchestration and notifications

### Device ###
I had a NodeMCU lying in my inbox so that's what I used.
Safe pins for relays: GPIO 4, 5, 12, 13, 14 (see ref. 1)
Temperature sensor: GPIO 2/D4 (see ref. 2)

### Requirements ###
- NodeMCU or other ESP based device - generally available
- Relay board (one relay per function you'd like to monitor/conrol). Got mine from local Bulgarian web shop [radev96.com](https://radev96.com)

### Future Development ###
- Moisture/Water Insulation - kids, fish, fishtanks, water, electricity…
- micro-usb port exposure for potential serial connection without the need for disassembly
- variable schedule (i.e. gradually increase the light hours from 6 to 8 over a period of 3 months)


### References ###
1. [ESP8266 Relay](https://randomnerdtutorials.com/esp8266-relay-module-ac-web-server/)
2. [Nodemcu ESP8266 DS18b20 Waterproof Temperature Sensor Monitoring](https://www.electroniclinic.com/nodemcu-esp8266-ds18b20-waterproof-temperature-sensor-monitoring/)
3. [ESP8266 Pinout Reference](https://randomnerdtutorials.com/esp8266-pinout-reference-gpios/)
4. [WiFi Smart Power Strip with NodeMCU](https://www.instructables.com/WiFi-Smart-Power-Strip-With-NodeMCU/)
