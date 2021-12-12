# Kcosit-K72H-Rugged-touch-firmware
Touch [Firmware file](firmware_00.fw) for for Linux Device


<RuggedPC>/<RuggedHandC62V>
---------------------------------------------

| Item                      | Description |
|---------------------------|-------------|
| Manufacturer              | RuggedPC |
| Device                    | RuggedHandC62V or Kcosit K72H |
| Website                   | hhttps://www.kcosit.com/Rugged-Handheld-PDA-Win10-1D2D-Barcode-Scanner-4GB-RAM-64GB-ROM-p1563970.html |
| Vendor driver (Windows)   | [SileadTouch.sys](SileadTouch.sys) |
| Extracted firmware        | [firmware_00.fw](firmware_00.fw) |
| Firmware for gslx680-acpi | [SileadTouch.sys](SileadTouch.sys) |
| Display resolution        | 1280X720 |
| Touch panel resolution    | unknown |
| Touch controller          | GSLxxxx, you should open your device and verify this |
| Multitouch support        | Yes (10 of recognized touch points)|
| Finger tracking           | No |
| Mirrored horizontally     | No |
| Mirrored vertically       | No |
| Axes swapped              | Yes |

 ## Instruction
 create a Folder
 
 `sudo mkdir /lib/firmware/silead`
  
  copy and rename [Firmware file](firmware_00.fw)
 
  `sudo cp firmware_00.fw /lib/firmware/silead/mssl1680.fw`
  
  make sure insalled these
 
  `sudo apt-get install xserver-xorg-input-evdev xserver-xorg-core`
  
  edit this part of 10-evdev.conf file
 
  `sudo nano /usr/share/X11/xorg.conf.d/10-evdev.conf` 
 
  `Section "InputClass"
        Identifier "evdev touchscreen catchall"
        MatchIsTouchscreen "on"
        MatchDevicePath "/dev/input/event*"
        Driver "evdev"
        Option "SwapXY" "0"
EndSection`
  
edit 99-calibration.conf
 
`sudo nano /usr/share/X11/xorg.conf.d/99-calibration.conf`

`Section "InputClass"
      Identifier "evdev touchscreen catchall"
      MatchIsTouchscreen "on"
      MatchDevicePath "/dev/input/event*"
      Driver "evdev"
      Option "InvertX" "1"
      Option "InvertY" "1"
      Option "Calibration" "15 875 15 1650"
      Option "SwapAxes" "1"
EndSection`

 reboot
 
 this currently only works under X11 no Wayland support
