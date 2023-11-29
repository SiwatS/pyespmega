# pyESPMega
This library provides a mean of communicating with the ESPMega Programmable Logic Controller through MQTT<br/>

## **Compatibility**
This library is compatible with:<br/>
- ESPMega R2.4 [2018] (Model e) with IoT FreedomOS v1.2+
- ESPMega R3.0 [2020] (All Model) with IoT Core LT OS V1.4
- ESPMega Plus R1.0 [2020] (All Model) with IoT Core LT+ OS V1.4
- ESPMega R4.0 [2023] (All Model) with IoT Core LT OS V2
- ESPMega PRO R2.0 [2020] (Model c) with IoT Core OS V1
- ESPMega PRO R3.3 [2023] (Model b,c) with IoT Core OS V2.2 (or above)

## **ESPMega Client Types**
There are two type of ESPMega client, ESPMega and ESPMega_standalone<br/>
### ESPMega
ESPMega class requires you to provide and maintain an MQTT connection
This class takes in a Paho-MQTT Client as an input argument<br/>
**Import and Initialization**
```
from espmegar3 import ESPMega
plc = ESPMega("/basetopic", MQTT_CLIENT)
```
### ESPMega_standalone
ESPMega_standalone create and maintain the required mqtt connection for you.
**Import and Initialization**
```
from espmegar3 import ESPMega_standalone as ESPMega
plc = ESPMega("/basetopic", "MQTT_SERVER", MQTT_PORT)
```
## **ESPMega Client Functions**
1. **digital_read(pin: int)** | Reads the digital value of a pin.
2. **digital_write(pin: int, state: bool) | Writes a digital value to a pin.
3. **analog_write(pin: int, state: bool, value: int)** | Writes an analog value to a pin.
4. **dac_write(pin: int, state: bool, value: int)** | Writes a DAC value to a pin.
5. **set_ac_mode(mode: str)** | Sets the AC mode. ("off", "fan_only", "cool")
6. **set_ac_temperature(temperature: int)** | Sets the AC temperature.
7. **set_ac_fan_speed(fan_speed: str)** | Sets the AC fan speed.
8. **get_ac_mode()** | Returns the current AC mode.
9. **get_ac_temperature()** | Returns the current AC temperature.
10. **get_ac_fan_speed()** | Returns the current AC fan speed.
11. **read_room_temperature()** | Reads the room temperature.
12. **read_humidity()** | Reads the humidity.
13. **send_infrared(code: dict)** | Sends an infrared code. Codes are a timing interval list in milliseconds
14. **request_state_update()** | Requests an update of the device state.
15. **get_input_buffer()** | Return the state of every input as a list
