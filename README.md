# esp8266

## Firmware

AT firmware: https://www.espressif.com/en/support/download/at
Datasheet: https://www.espressif.com/sites/default/files/2a-esp8266-sdk_getting_started_guide_en_0.pdf

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

Flash it:

```
$ sudo esptool.py -p /dev/ttyUSB0 write_flash 0x00000 boot_v1.7.bin  0x01000 at/1024+1024/user1.2048.new.5.bin  0xfc000  esp_init_data_default_v08.bin  0xfe000 blank.bin
esptool.py v2.6
Serial port /dev/ttyUSB0
Connecting.......
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
Compressed 4080 bytes to 2936...
Wrote 4080 bytes (2936 compressed) at 0x00000000 in 0.3 seconds (effective 123.6 kbit/s)...
Hash of data verified.
Compressed 455508 bytes to 324659...
Wrote 455508 bytes (324659 compressed) at 0x00001000 in 28.9 seconds (effective 126.0 kbit/s)...
Hash of data verified.
Compressed 128 bytes to 75...
Wrote 128 bytes (75 compressed) at 0x000fc000 in 0.0 seconds (effective 95.8 kbit/s)...
Hash of data verified.
Compressed 4096 bytes to 26...
Wrote 4096 bytes (26 compressed) at 0x000fe000 in 0.0 seconds (effective 5342.0 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...
```

