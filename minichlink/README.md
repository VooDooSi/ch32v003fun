# minichlink

A free, open mechanism to use the CH-LinkE $4 programming dongle for the CH32V003.

If on Linux, make sure to install the `99-WCH-LinkE.rules` build rule to `/etc/udev/rules.d/`

On Windows, if you need to you can install the WinUSB driver over the WCH interface 1.

The exe here is about 12kB and contains everything except for the libusb driver.  In Linux you need `libusb-1.0-dev`.

## Usage

```
Usage: minichlink [args]
 single-letter args may be combined, i.e. -3r
 multi-part args cannot.
 -3 Enable 3.3V
 -5 Enable 5V
 -t Disable 3.3V
 -f Disable 5V
 -Q [serial number of WCHLinkE] - select specific WCHLinkE programmer
 -c [serial port for Ardulink, try /dev/ttyACM0 or COM11 etc]
 -C [specified programmer, eg. b003boot, ardulink, esp32s2chfun]
 -u Clear all code flash - by power off (also can unbrick)
 -E Erase chip
 -b Reboot out of Halt
 -e Resume from halt
 -a Reboot into Halt
 -A Go into Halt without reboot
 -D Configure NRST as GPIO
 -d Configure NRST as NRST
 -i Show chip info
 -s [debug register] [value]
 -m [debug register]
 -T Terminal Only (must be last arg)
 -G Terminal + GDB (must be last arg)
 -P Enable Read Protection
 -p Disable Read Protection
 -S set FLASH/SRAM split [FLASH kbytes] [SRAM kbytes]
 -w [binary image to write] [address, decimal or 0x, try0x08000000]
 -r [output binary image] [memory address, decimal or 0x, try 0x08000000] [size, decimal or 0x, try 16384]
   Note: for memory addresses, you can use 'flash' 'launcher' 'bootloader' 'option' 'ram' and say "ram+0x10" for instance
   For filename, you can use - for raw (terminal) or + for hex (inline).
 -X [programmer-specific command, for esp32-s2 programmer, -X ECLK:1:0:0:8:3 for 24MHz clock out]
```
 
