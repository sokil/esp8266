# esp8266

## Firmware

### Official firmware

* AT firmware: https://www.espressif.com/en/support/download/at
* Datasheet: https://www.espressif.com/sites/default/files/2a-esp8266-sdk_getting_started_guide_en_0.pdf

### NodeMCU

https://github.com/nodemcu/nodemcu-firmware

## Terminal

```
minicom -D /dev/ttyUSB0
Port: /dev/ttyUSB0
Baud Rate (Data Rate): 115200
Data Bits: 8
Parity: none
Stop bits: 1
Flow control: none
```

## AT commands

## Flasher

Initial boot address is 0x00000.

### ESPTool

https://github.com/espressif/esptool

```
sokil@hp:~$ sudo esptool.py -p /dev/ttyUSB0 flash_id
esptool.py v2.6
Serial port /dev/ttyUSB0
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
MAC: 18:fe:34:d3:1f:b5
Uploading stub...
Running stub...
Stub running...
Manufacturer: e0
Device: 4014
Detected flash size: 1MB
Hard resetting via RTS pin...
```

Download latest firmware at: https://www.espressif.com/en/support/download/at?keys=&field_type_tid%5B%5D=14

Or extract local AT_V1.1_on_ESP8266_NONOS_SDK_V1.5.4.zip.

Flash it:

```
$ sudo esptool.py -p /dev/ttyUSB0 write_flash 0x00000 boot_v1.5.bin  0x01000 512+512/user1.1024.new.2.bin  0xfc000  esp_init_data_default.bin  0x7e000  blank.bin 0xfe000 blank.bin
esptool.py v2.6
Serial port /dev/ttyUSB0
Connecting....
Detecting chip type... ESP8266
Chip is ESP8266EX
Features: WiFi
MAC: 18:fe:34:d3:1f:b5
Uploading stub...
Running stub...
Stub running...
Configuring flash size...
Auto-detected Flash size: 1MB
Flash params set to 0x0020
Compressed 3232 bytes to 2336...
Wrote 3232 bytes (2336 compressed) at 0x00000000 in 0.2 seconds (effective 122.2 kbit/s)...
Hash of data verified.
Compressed 399204 bytes to 286943...
Wrote 399204 bytes (286943 compressed) at 0x00001000 in 25.6 seconds (effective 125.0 kbit/s)...
Hash of data verified.
Compressed 128 bytes to 77...
Wrote 128 bytes (77 compressed) at 0x000fc000 in 0.0 seconds (effective 93.5 kbit/s)...
Hash of data verified.
Compressed 4096 bytes to 26...
Wrote 4096 bytes (26 compressed) at 0x0007e000 in 0.0 seconds (effective 5224.4 kbit/s)...
Hash of data verified.
Compressed 4096 bytes to 26...
Wrote 4096 bytes (26 compressed) at 0x000fe000 in 0.0 seconds (effective 5422.5 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...

```



