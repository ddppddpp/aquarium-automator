# aquarium-automator
A device that helps monitor and automate basic aquarium/ fish tank needs


- Monitor
  - Temperature

- Automations
  - relay triggering
  - thermostat
- light schedule
  - fixed schedule
- Various reminders for chores, i.e.
  - Feeding
  - Water Cleaning/ Maintenance
  
### Platform ###
- [ESPHome](https://esphome.io) for sensor data and relay trigger
- [HomeAssistant](https://www.home-assistant.io) for schedule orchestration and notifications


### Requirements ###
- NodeMCU or other ESP based device - generally available. I had a NodeMCU lying in my inbox so that's what I used.
- Relay board (one relay per function you'd like to monitor/conrol). Got mine from local Bulgarian web shop [radev96.com](https://radev96.com)
- A 'dallas' DS18B20 single wire temperature sensor - despite the name it comes with 3 wires - V+,V-, Data
- A number of dupont wires available from your local maker's store or online
- A 5V Power Supply unit that will supply power to the NodeMCU
- One power outlet per relay (in my case I also inluded an extra one that is always on for air supply). A power strip might also do the job if you have one in which outlets can be powered off individually
- A box to put all these items in

### Assembly ###

Safe pins for relays: GPIO 4, 5, 12, 13, 14 (see ref. 1)
Temperature sensor: GPIO 2/D4 (see ref. 2)



### Future Development ###
- Moisture/Water Insulation - kids, fish, fishtanks, water, electricity…
- micro-usb port exposure for potential serial connection without the need for disassembly
- variable schedule (i.e. gradually increase the light hours from 6 to 8 over a period of 3 months)
- Monitor water quality (ph?)

### References ###
1. [ESP8266 Relay](https://randomnerdtutorials.com/esp8266-relay-module-ac-web-server/)
2. [Nodemcu ESP8266 DS18b20 Waterproof Temperature Sensor Monitoring](https://www.electroniclinic.com/nodemcu-esp8266-ds18b20-waterproof-temperature-sensor-monitoring/)
3. [ESP8266 Pinout Reference](https://randomnerdtutorials.com/esp8266-pinout-reference-gpios/)
4. [WiFi Smart Power Strip with NodeMCU](https://www.instructables.com/WiFi-Smart-Power-Strip-With-NodeMCU/)
