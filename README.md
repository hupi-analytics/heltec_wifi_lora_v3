# heltec_wifi_lora_v3
# heltec_wifi_lora_v3

For HELTEC_WIFI_LORA_32_V3 : I forked from WIFIKIT and reorganized to be compatible with Platformio 6.2

You will find in boards/heltec_wifi_lora_32_V3.json to add in your .platformio/boards 

Exemple for my platform.ini
```
; PlatformIO Project Configuration File
;
;   Build options: build flags, source filter
;   Upload options: custom upload port, speed and extra flags
;   Library options: dependencies, extra library storages
;   Advanced options: extra scripting
;
; Please visit documentation for the other options and examples
; https://docs.platformio.org/page/projectconf.html

[env:esp32-s3-devkitc-1]
platform = espressif32
;platform_packages = framework-arduinoespressif32@3.20005.220925
board = heltec_wifi_lora_32_V3
framework = arduino
monitor_speed = 115200
upload_speed = 115200
build_flags = 
	-D REGION_EU868
	-D ACTIVE_REGION=LORAMAC_REGION_EU868
	-D LoRaWAN_DEBUG_LEVEL=0
	-D LORAWAN_PREAMBLE_LENGTH=8
	-D LORAWAN_DEVEUI_AUTO=0
	-D WIFI_LoRa_32_V3
	-L /Users/robino/.platformio/packages/framework-arduinoespressif32/tools/sdk/esp32s3/lib/
	-L /Users/robino/Downloads/esp32-0.0.7/tools/sdk/esp32s3/lib/
	-lheltec
	-lxtensa	
	-Wno-error=unused-variable
	-Wno-error=deprecated-declarations
	-Wno-unused-parameter
	-Wno-sign-compare
	-Wno-error=unused-but-set-variable
	-Ilib/heltec_wifi_lora_32_V3/src
lib_deps = heltecautomation/Heltec ESP32 Dev-Boards@^1.1.1
lib_ldf_mode = deep+
```
