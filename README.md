# esp8266

## Firmware

https://www.espressif.com/en/support/download/at

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


