
## Hardware
### Steppers
stepper partnumber: SM15DD

motor 1: 
1: black - white
2: red - blue

info on stepper: https://bends.se/?page=notebook/electronics/stepper-2
2 phases
rated voltage: 5V
ohmic resistance per phase: 10 ohm
degrees per step: 18°

### Creality V2.0 Mainboard

#### Power
The Creality V2.0 motherboard must be connected to 12V power via the dual screw terminal on the bottom left.
The board can not be powered from the ICSP or micro USB headers.
When the board is powered the blue "PWR" LED should light up permanently.

#### ICSP-Header

For programming the AtMega 2560-16AU without a bootloader power and an ICSP/ISP-programmer is needed.  
The programmer's target cable should be connected to the header labelled "ICSP" next to the processor with the nob of the connector facing the processor, see the picture below.
![IMG_20230915_171140](https://github.com/Jajaho/Durstloeschinator/assets/28218941/cf5f08ae-c136-44af-a5f7-e77eaf539c6f)


#### Stepper Drivers
A4988
[Datasheet](https://www.pololu.com/file/0J450/a4988_DMOS_microstepping_driver_with_translator.pdf)

Load Supply Voltage Range VBB Operating 8 – 35 V **PROBLEM**
-> Maybe use TB6612FNG
-> TMC2209 Voltage Range 4.75… 29V DC
-> TMC2202, TMC2208, TMC2224 Voltage Range 4.75… 36V DC [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/TMC2202_TMC2208_TMC2224_datasheet_rev1.14.pdf)

current adjustment:
Single leg of the smd poti is connected to pin 17 of the driver.
turning poti to the left: resistance between top right leg and single leg on the left increases.