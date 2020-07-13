<!-- Please do not change this html logo with link -->
<a href="https://www.microchip.com" rel="nofollow"><img src="images/microchip.png" alt="MCHP" width="300"/></a>

# Noise Countermeasures for ADC Applications

This repository will explain how and when to use the powerful noise suppression features available on the Microchip tinyAVR® 1-series and megaAVR® 0-series ADCs. In these ADCs, the input signal is fed through a sample-and-hold circuit which ensures that the input voltage to the ADC is held at a constant level during sampling. The ADC supports sampling in bursts where a configurable number of conversion results are accumulated into a single ADC result (sample accumulation). Further, a sample delay can be configured to tune the ADC sampling frequency associated with a single burst. This to tune the sampling frequency away from any harmonic noise aliased with the ADC sampling frequency (within the burst) from the sampled signal. An automatic sampling delay variation feature can be used to randomize this delay to slightly change the time between samples.

<br/> Topics covered include using the ADC hardware sample accumulator to filter out zero mean random noise and surpassing harmonic noise through tuned sampling delays or automatic sampling delay variation. The noise filtering is demonstrated by using an example source code and plotting a graph of ADC samples in *MPLAB Data Visualizer*. This is explained in detail in the Application Note [*AN2551 - Noise Countermeasures for ADC Applications*](https://www.microchip.com/DS00002551) by Microchip. The code is run on a ATtiny817 Xplained Pro board. 

## Related Documentation

- [AN2551 - Noise Countermeasures for ADC Applications](https://www.microchip.com/DS00002551)
- [ATtiny817 Device Page](https://www.microchip.com/wwwproducts/en/ATtiny817)

## Software Used

- [MPLAB® X IDE](http://www.microchip.com/mplab/mplab-x-ide) 5.40 or later
- [ATtiny DFP](http://packs.download.atmel.com/) 1.6.316 or later
- [MPLAB® XC8](http://www.microchip.com/mplab/compilers) 2.20 or a later
- [AVR/GNU C Compiler](https://www.microchip.com/mplab/avr-support/avr-and-arm-toolchains-c-compilers) 5.4.0 or later
- [MPLAB® Data Visualizer](https://gallery.microchip.com/packages/MPLAB-Data-Visualizer-Standalone(Windows)/) 1.1.793 or later
- [Atmel Studio Data Visualizer](https://www.microchip.com/mplab/avr-support/data-visualizer) 2.20.674 or later

## Hardware Used

- [ATtiny817 Xplained Pro](https://www.microchip.com/DevelopmentTools/ProductDetails/attiny817-xpro)
- Micro-USB cable (Type-A/Micro-B)

## Operation

1. Connect the ATtiny817 Xplained Pro board to the PC using the USB cable.

2. Download the zip file or clone the example to get the source code.

3. Open the project in MPLAB X IDE.

4. Follow the application note [AN2551 - Noise Countermeasures for ADC Applications](https://www.microchip.com/DS00002551) to configure the code for different types of noise.

5. Build the solution and program the ATtiny817. 

6. Plot the ADC results:
    - In *Atmel Studio* go to *Tools* and open *Data Visualizer*. Configure *Data Visualizer* to plot a graph of the ADC samples. Refer to Appendix A in the Application Note [AN2551 - Noise Countermeasures for ADC Applications](https://www.microchip.com/DS00002551) on how to do this. Refer to [Atmel Studio Data Visualizer User's Guide](https://www.microchip.com/DS40001903) for help with *Data Visualizer*.

    - Alternatively: Open [*MPLAB® Data Visualizer*](https://gallery.microchip.com/packages/MPLAB-Data-Visualizer-Standalone(Windows)/). Load the workspace with the configuration file that followed the code example. Make sure you are using the right COM-port. Refer to [MPLAB® Data Visualizer User's Guide](https://www.microchip.com/DS50003001) for help with *Data Visualizer*.

7. Try plotting different signals by combining the use of random noise, periodic noise, sample accumulation and sampling delay. You do this by reconfiguring the macro definitions before building and programming the device. The new graph will be plotted in *Data Visualizer*.


## Conclusion
We have now looked at how to use the powerful noise suppression features available on the Microchip tinyAVR® 1-series and megaAVR® 0-series ADCs. The example described how to use the ADC hardware sample accumulator to filter out zero mean random noise and surpassing harmonic noise through tuned sampling delays or automatic sampling delay variation.