# STM32_ADC

## STM32 ADC Measurements

## Measurement Condition
### Hardware Setup
- The used board is STM32F446RE-Nucleo 

~~STM32F407ZGT6 soldered on a test board (with only a minimum number of other
hardware components)~~
- Power Supply range: 3.3 V
- fADC = 36 MHz
- Clock source =  external clock (8 MHz) provided by a generator, PLL is enabled, fCPU = 144 MHz
- Three fixed analog input voltages are tested: 0.3 V, 1.65 V and 3 V
### Firmware Setup
- ADC1 channel 0 is used  in single conversion mode
- 50000x4 acquisitions were taken for each fixed analog input voltage

*All tests were done with fADC = 36 MHz, sampling time = 3 ADC cycles and ADC resolution = 12 bits in order to achieve the fastest ADC conversion (2.4 Msps).*
## Results
The following measurements were considered while evaluating the impact of three different
ART configurations on the ADC accuracy:
- ART ON: (data cache + instruction cache + prefetch) ON
- ART OFF: (data cache + instruction cache + prefetch) OFF
- (Data cache + instruction cache) ON + prefetch OFF
- FLASH Memory is used and ART ON
- FLASH Memory is used and (Data cache + instruction cache) ON + prefetch OFF
- FLASH Memory is used and ART ON - Option 1 Enable
- FLASH Memory is used and ART ON - Option 2 Enable



## Measurement Conclusion
![alt text](https://github.com/FebbyMadrin/STM32_ADC/blob/master/results/result.PNG "result")
![alt text](https://github.com/FebbyMadrin/STM32_ADC/blob/master/results/result1.PNG "graphics")



## References:
1. STM32F446xC/E - Datasheet - production data
    ARM® Cortex®-M4 32b MCU+FPU, 225DMIPS, up to 512kB Flash/128+4KB RAM,
    USB OTG HS/FS, 17 TIMs, 3 ADCs, 20 comm. interfaces
2. RM0390 - Reference manual
3. STM32F446xC/xE - Errata sheet
4. AN4073 - Application note
    How to improve ADC accuracy when using STM32F2xx and
    STM32F4xx microcontrollers
5. AN2834 - Application note
    How to get the best ADC accuracy
    in STM32 microcontrollers

<!-- ## Notes:
1. to avoid the unintended disturbance:
    - put the device far away from EMC Sources, like fan laptop
    - the ADC cable must not contacted by another cable, to avoid crosstalk

    - pada counting ke 1800an sering terjadi galat error -->