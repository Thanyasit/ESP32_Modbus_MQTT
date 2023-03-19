# ESP32_Modbus_MQTT
<h1>Description</h1>
This code is written for the ESP32 and is intended to read values from a Modbus device and publish them to an MQTT broker. The code uses the ModbusMaster library to communicate with the Modbus device and the PubSubClient library to publish to the MQTT broker.

<h1>Usage</h1>
The code begins by including the necessary libraries and defining some constants. The <b>setup_wifi()</b> function connects to a WiFi network using the <b>WiFi</b> library. The <b>reconnect()</b> function attempts to connect to an MQTT broker using the <b>PubSubClient</b> library.

The <b>preTransmission()</b> and <b>postTransmission()</b> functions are used to control the MAX485 transceiver, which is used to communicate with the Modbus device. The <b>setup()</b> function initializes the serial communication, connects to the WiFi network and MQTT broker, and reads values from the Modbus device. It then publishes these values to the MQTT broker using the <b>client.publish()</b> function.

The code also includes functions for converting 32-bit integers to floats and floats to 32-bit integers. These functions are used to convert the Modbus values to a format that can be published to the MQTT broker.

To put the ESP32 into deep sleep mode, the <b>esp_deep_sleep_start()</b> function is used. The <b>esp_sleep_enable_timer_wakeup()</b> function is used to set the sleep interval.

To use this code, you will need to modify the following constants in the setup() function:

<b>ssid</b> - the name of your WiFi network
<b>password</b> - the password for your WiFi network
<b>mqtt_server</b> - the IP address of your MQTT broker
You will also need to modify the following lines in the <b>client.connect()</b> function in the <b>reconnect()</b> function:

<b>"NO4"</b> - this is the client ID used to connect to the MQTT broker. You can change this to any unique string.
Note that the code is written to read and publish values from a specific Modbus device. You will need to modify the code to read and publish values from your own Modbus device. You can use the <b>readInputRegisters()</b> function to read values from your Modbus device, and the <b>client.publish()</b> function to publish these values to the MQTT broker.

<h1>License</h1>
This code is licensed under the MIT License. See the LICENSE file for details.
