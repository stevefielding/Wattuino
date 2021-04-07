# Optiboot

[Optiboot](https://github.com/Optiboot/optiboot) is a small serial bootloader designed for Atmel AVR microcontrollers.

This project is a modified Optiboot with baud rate fixed at 57600.  
User code boot time is configured for 8s.  
Configured for multiple optiboot nodes on a shared RS485 network. Each node is identified by an 8-bit NodeID that is programmed into
EEPROM.  
Optiboot configured to run after power up. So there is an 8s delay before user code is booted.
The Optiboot project is released under GPL license.
Code uploaded via the bootloader is not subject to any license issues.

**Credits**
```
Although it has evolved considerably, Optiboot builds on the original work of Jason P. Kyle (stk500boot.c), Arduino group (bootloader), Spiff (1K bootloader), AVR-Libc group and Ladyada (Adaboot).

Optiboot is the work of Peter Knight (aka Cathedrow). Despite some misattributions, it is not sponsored or supported by any organisation or company including Tinker London, Tinker.it! and Arduino.
Maintenance of Optiboot was taken over by Bill Westfield (aka WestfW) in 2011.
```

## ISP Pins of ATmega328
```
MOSI: PB3 / D11
MISO: PB4 / D12
SCK:  PB5 / D13
RST:  PC6 / Reset
```

## Fuse Settings for ATmega328PB
```
Extended: 0xF4
High:     0xD4
Low:      0xBF
Lockbits: 0xCF (LPM and SPM prohibited in Boot Section)
```

## AVRdude Parameters for ATmega328PB
```
avrdude -c /home/pi/vv8/atom_scripts/avrdude_atmega328pb_conf/avrdude.conf \
-v -patmega328pb -carduino -P/dev/ttyS0 -b57600 \
-Uflash:w:/home/pi/vv8/progfiles/Blink_pod.ino.hex:i -z 1

```
