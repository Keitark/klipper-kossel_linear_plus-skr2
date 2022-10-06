# klipper-kossel_linear_plus-skr2

## About this file
This Klipper printer configuration file is for Anycubic Kossel Linear Plus + SKR2 Boards and modified from following example.

* https://github.com/Klipper3d/klipper/blob/master/config/printer-anycubic-kossel-plus-2017.cfg
* https://github.com/Klipper3d/klipper/blob/master/config/generic-bigtreetech-skr-2.cfg

Some of settings are from below Lukas's guide and walterlootk's settings

* Lukas's https://www.lpomykal.cz/anycubic-kossel-klipper-configuration/
* walterlootk's https://github.com/walterlootk/SKR2-Marlin-2.0.9.3-Delta

Please compile Klipper firmware for stm32f407 series.

Confirmed with Fystec TMC2208 steppers, but might work with most of TMC steppers.

To whom build printer.cfg from scratch, do not forget to add follwing.

```
[output_pin motor_power]
pin: PC13
value: 1
```

## Brief memo for installation

Recommend to install [Fluidd](https://docs.fluidd.xyz/).
Below summarizes the flow should be done here after. 

1. Download Fluidd installer
1. Burn Rapsberry Pi image to SD card provided from above.
1. Boot Raspberry Pi and login to the fluidd pi environment over that pi.
1. Make Klipper firmware on the pi with commmon setting for SKR2 board (no need for printer.cfg at this time).
1. Transfer the Klipper firmware to your Kossel via SD card.
1. Then add printer.cfg throguh Fluidd web interface.
1. After rebooting firmware and Klipper, your Kossel shall be fully controllable from Fluidd UI.

## Brief memo for calibration

Please read through https://www.klipper3d.org/Delta_Calibrate.html

My conclusion is that "Forget the probe, just calibrate manually." 
```
G28
DELTA_CALIBRATE METHOD=manual
```
All you have to do is so-called 'paper test' at a few points, which takes only a few minutes.

Then, do not forget to store.
```
SAVE_CONFIG
```

## Known issue

CANCEL_PRINT semms to not working at this time.



