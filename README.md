# dspCore
Build arround the ADAU1452 / ADAU1462 / ADAU1466 from Analog Devices with balanced 2-in / 6-out as well as support for I2S, SPDIF and TDM. This board is optimized for low noise performance and in particular to support all features of the [ICEpower 300A1](https://shop.icepoweraudio.com/product/300a1/) and similary amplifier modules.<br>

First prototyp build in 2014, redesigned in 2016 and the lastest version in 2021, mostly to substitute conflict materials like tantalum. The I2S input was tested with RaspberryPi 3/4/5 and ESP32S3.

## Design requirements
 - Balanced  2-in / 6-out 
 - Low idle noise without active mute circuit (compression driver requirement @ >100dB/1W/1m)
 - Stereo 3-way active x-over with FIR support for mid-high
 - Flexible I2S interaface
 - 48V DC batterie operation


## Hardware
![dspCore](documentation/images/pcb_populated.jpeg)

- DSP:  [ADAU1466](https://www.analog.com/en/products/adau1466.html) or [ADAU1452](https://www.analog.com/en/products/adau1452.html)
- A/D:  [CS5381](https://www.cirrus.com/products/cs5381/)
- D/A:  [CS4389](https://www.cirrus.com/products/cs4398/)
- OPA:  [OPA1612](https://www.ti.com/product/de-de/OPA1612/part-details/OPA1612AID)
- XO:   [CCHD-957](https://www.crystek.com/home/oscillator/clockdetail.aspx?pn=CCHD-957)
- USB:  [CY7C68013A](https://www.infineon.com/cms/de/product/universal-serial-bus/usb-2.0-peripheral-controllers/ez-usb-fx2lp-fx2g2-usb-2.0-peripheral-controller/cy7c68013a-56ltxc/)

## Measurements
__The Poor Engineer's Distortion Analyzer__ is a distortion analyzer based on the idea of KJBob (@ ADI EngineeringZone).<br><br>
This is a loop back measurement (DSP->D/A->A/D->DSP). The readings are close to the datasheet specifications of the CS4398, but of course there is an uncertainty without external verification.<br>

### DUT
![dspCore](documentation/measurements/dut.jpeg)<br>

### 1V RMS
```0.000527918% THD+N = -105.54dB (a-weighted)```
<br><br>
![dspCore](documentation/measurements/1vrms_dspCore(diff)_thd+n.jpeg)<br>
### 2V RMS
```0.000626624% THD+N = -104.06dB (a-weighted)```
<br><br>
![dspCore](documentation/measurements/2vrms_dspCore(diff)_thd+n.jpeg)<br>

## To do

- Port eagle -> KiCad

## Usecase
![dspCore](documentation/images/tonkraftwerk.jpeg)<br>
![dspCore](documentation/images/tonkraftwerk_electronics.jpeg)<br>

## License

The hardware is licensed under CC BY-SA 4.0 
