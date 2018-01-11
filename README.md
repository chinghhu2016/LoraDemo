# README #

PhoneGap app for reading parking status from a MQTT server.

## Content ##
* Lora devices
* MQTT servers

## Lora devices ##
* Lora node + sketch "lora_toggle_device"
* Lora gateway + sketch "ist_mqtt_upload"

## MQTT server ##
* A public MQTT server with WebSocket access, so that it can be subscribe from a browser or phonegap app.
* Available public servers: https://github.com/mqtt/mqtt.github.io/wiki/public_brokers
* The first release uses "iot.eclips.org"
* For demo in China, you need to find a public MQTT broker with websocket support in China.
* To change MQTT broker, you need to change this path in sketch "ist_mqtt_upload" and index.html in this project.

## MQTT message ##
1. Topic: isentek/device/GATEWAY_ID
2. Payload: NODE_ID/Timestamp/1 or 0
3. GATEWAY_ID is set in sketch "ist_mqtt_upload", while NODE_ID is set in sketch "lora_toggle_device".





