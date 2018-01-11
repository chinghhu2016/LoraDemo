# README #

PhoneGap app for reading parking status from a MQTT server.

The data flow is like
Lora node --- (lora network) ---> Lora Gateway --- (internet) ----> MQTT server ---- (internet) ----> Demo App

## Content ##
* Lora devices
* MQTT servers
* MQTT message
* Video stream
* Build Environment

## Lora devices ##
* Lora node + sketch "lora_toggle_device"
* Lora gateway + sketch "ist_mqtt_upload"
* Sketchbook location: https://bitbucket.org/chinghhu/ist_arduino_sketchbook
* For Lora gateway, it requires internet access in order to publish to MQTT server.  Plug network cable to "WAN" port on the device.
* For Lora gateway, you will need password to flash arduino part. The password is "dragino".

## MQTT server ##
* A public MQTT server with WebSocket access, so that it can be subscribe from a browser or phonegap app.
* Available public servers: https://github.com/mqtt/mqtt.github.io/wiki/public_brokers
* The first release uses "iot.eclips.org"
* For demo in China, you need to find a public MQTT broker with websocket support in China.
* To change MQTT broker, you need to change this path in sketch "ist_mqtt_upload" and index.html in this project.
* "test.mosquitto.com"'s websocket service seems buggy, according to discussion on the web, and my own experience. So don't bother to use it.

## MQTT message ##
1. Topic: isentek/device/GATEWAY_ID
2. Payload: NODE_ID/Timestamp/1 or NODE_ID/Timestamp/0
3. GATEWAY_ID is set in sketch "ist_mqtt_upload", while NODE_ID is set in sketch "lora_toggle_device".

## Video stream ##
* It is found on the web, you need to change the url in index.html to point to the right source.

# Build Environment ##
* I did all the build activitis on cloud services. With those services, you don't even need to setup local environment for development, except some for debugging purpose.
* I have tried monaca.io and PhoneGap Build. Both are good. Though free account does have its own limitation (number of build, package size, etc), but it is enough for our use.



