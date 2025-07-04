# MicroFC SiPM Array Board

Carrier board for a 2 x 2 array of the 6 mm C-Series MICROFC-60035-SMT silicon photomultipliers by [onsemi](https://www.onsemi.com/pdf/datasheet/microc-series-d.pdf).

PCB size is 20 x 20 mm. The solder pads for the SiPM are slightly bigger than they need to so that you can easily hand-solder everything! You can buy all the parts and the PCB using [Kitspace](https://kitspace.org/opengammaproject/MicroFC-SiPM-Array-Board) (non-affiliated).

<p align="center">
  <img alt="Front Side PCB" title="Front Side PCB" src="docs/pcb_front.jpg" height="300px">
  <img alt="Back Side PCB" title="Back Side PCB" src="docs/pcb_back.jpg" height="300px">
</p>

<p align="center">
  <img alt="Front Side PCB Rendering" title="Front Side PCB Rendering" src="docs/sipm1.png" height="300px">
  <img alt="Back Side PCB Rendering" title="Back Side PCB Rendering" src="docs/sipm2.png" height="300px">
  <img alt="Back Side 3D Rendering" title="Back Side 3D Rendering" src="docs/sipm3.png" height="300px">
</p>

On the front side there are only the 4 sensors themselves while all the other parts are on the back. This ensures good optical contact and light-tight sealing. The PCB includes some bias filtering for the 4 SiPMs that must also be soldered and an optional temperature compensation circuit! The temperature compensation takes care of the change in bias voltage and therefore gain depending on the ambient temperature (~21mV/K).

If you want to use the added temperature compensation, be sure to solder all the components to the board and connect your power to the `VCC` pad. For setting the correct voltage, you can check the `C` pad on the PCB, but be sure to do this either before soldering the SiPMs or only when the SiPMs are not exposed to ANY light, otherwise they'll saturate immediately and pass a high current. You can also check the voltage on your power supply itself of course, but due to the nature of the compensation circuitry, the applied voltage to the SiPMs will then be a couple of 100 millivolts lower than what is shown. If you don't want to use the extra circuitry, you can apply your power directly to the `C` pad on the PCB. However, you still need to solder the low-pass filters for that (R2 - R5 and C2 - C5) and C1. The voltage will then be exactly what you apply.

The SiPMs all share a common cathode with bulk decoupling and an R-C low-pass filter each. The anodes are **not** connected together so that you can have some spatial resolution if you want to. You could mount a very small scintillator to each sensor and then have a four pixel gamma-ray camera, yay I guess?!

However, you can also connect all four SiPMs in parallel to a common output by connecting the anode pads to each other, e.g. by connecting the wires that you solder to the pads. You will obviously lose any spatial resolution, but this way you can use it just like a single SiPM in the 4P configuration. SNR should be pretty much the same as with a single SiPM, but your active area will be 4x that of a single one!

To orient the SiPM correctly, look at the notches at the side of the plastic casing. There are 2 lines at the dot right here, that must be matched up with the dot on the PCB. There are numbered dots on the PCB that have to be matched up with that.

<p align="center">
  <img alt="SiPM Orientation" title="SiPM Orientation" src="docs/SiPM-orientation.jpg" width="49%" align="top">
  <img alt="Assembled SiPM array board" title="Assembled SiPM array board" src="docs/assembly.jpg" width="49%">
</p>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/J3J61GLR3G)
