# charge-stopper
Limit laptop battery charge with a Sonoff ESP8266 smart switch


## Flashing Sonoff

Steps to install micropython on a Sonoff.

0. erase flash `esptool.py --port /dev/ttyUSB0 erase_flash`
1. check device type with `esptool.py --port /dev/ttyUSB0 flash_id`  . In case of`Manufacturer: 5e` use 2a, otherwise 2b.
2. Flash firmware
    
    a. `esptool.py --port /dev/ttyUSB0 --baud 460800  write_flash -fs 1MB -fm dout 0x0 FIRMWARE.bin `
    
    b. `esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect 0 FIRMWARE.bin`
    
3. connect to device `picocom /dev/ttyUSB0 -b 115200`
