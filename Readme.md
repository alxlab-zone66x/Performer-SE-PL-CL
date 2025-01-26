# Micromac Performer SE/Plus/Classic Clone

This is a recreation of the MicroMac SE/Plus/Classic accelerator.  
The schematics have been reverse engineered and a new PCB was created based on the schematics.

![fully populated board](Performer_populated.jpg)

The provided PCB files are licensed under CC-BY-NC-SA - they are NOT intended for commercial use.  

  

## Notes on GALs and jumpers

The original GALs have been dumped. GAL16V8-15 as well as PALCE16V8-15 have been tested as suitable replacement.
Faster/slower chips as well as ATF16V8 of any speed haven't been tested so far.

U3, U4, U5 and U6 are mandatory. U7 is only needed for operation in Macintosh Plus and Classic.
Close SJ2 if U7 isn't installed. SJ2 HAS to be open when U7 is installed.

Close SJ1 to run the optional 68882 off the 16MHz accelerator clock.
Install an oscillator and open SJ1 to run the 68882 at any speed.
The original design used 25MHz which has been verified to work on the clone as well.

I have not found a socket that allows secure installation over the PLCC CPU in the Macintosh Classic.
Proper operation has been tested in the Macintosh Plus and SE but so far not on the Classic.



## Board Files

The provided gerber files have been generated using the JLCPCB EAGLE cam job files.  

The Kicad project files are placed inside the `kicad` folder. It's been slightly tweaked from the original Eagle project to pass DRC. The silkscreen for the Macintosh Classic and Macintosh Plus were moved to the bottom.

| Board Revision                | Description                                                  |                                                              |
| :---------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Performer PL-CL-SE            | Original recreation by Bolle.                                | [gerbers and bom](production/Performer_PL-CL-SE.zip)         |
| Performer SE v1.0 socket pga  | SE only, 2 layers, PGA FPU, PGA CPU, PLCC-20 through-hole sockets | [gerbers and assembly](production/Performer-SE_v1.0_socket-pga.zip) |
| Performer SE v1.1 socket pga  | SE only, 2 layers, PGA FPU, PGA CPU, PLCC-20 through-hole sockets | [gerbers and assembly](production/Performer-SE_v1.1_socket-pga.zip) |
| Performer SE v1.0 socket plcc | SE only, 2 layers, PLCC FPU, PGA CPU, PLCC-20 through-hole sockets | [gerbers and assembly](production/Performer-SE_v1.0_socket-plcc.zip) |
| Performer SE v1.1 socket plcc | SE only, 2 layers, PLCC FPU, PGA CPU, PLCC-20 through-hole sockets | [gerbers and assembly](production/Performer-SE_v1.1_socket-plcc.zip) |



## Bill of Materials

### Performer SE

Parts shared between the Performer SE design variations.

| Quantity | Description                                     | Designators                                                  | Product Number                                               |
| :------- | ----------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 4        | 100uF 6.3v 1206 mlcc                            | C1, C2, C3, C4                                               |                                                              |
| 5        | 0.1uF 6.3v 1206 mlcc                            | C5, C6, C7, C8, C9                                           |                                                              |
| 18       | 4.7kOhms 1/4W 1206 resistor                     | R1, R2, R3, R4, R5, R6, R7, R8, R9, R10, R11, R12, R13, R14, R15, R16, R17, R18 |                                                              |
| 4-6      | 0.5mm press-fit pin socket (optional)           | QG1                                                          | [0531-0-15-15-31-27-10-0](docs/datasheets/Mill-Max_0531-0-15-15-31-27-10-0.pdf) |
| 1        | 25MHz oscillator 8-pin or 14-pin dip (optional) | QG1                                                          | [ECS-2200B-250](docs/datasheets/ECS_ECS-2200B-250.pdf), [ECS-100AX-250](docs/datasheets/ECS_ECS-100AX-250.pdf) |
| 1        | pga-128 through-hole socket (optional)          | U1                                                           |                                                              |
| 4        | plcc-20 through-hole socket                     | U3, U4, U5, U6                                               | [PLCC-20-AT](docs/datasheets/Adam-Tech_PLCC-20-AT.pdf)       |

### Performer SE - PLCC FPU

| Quantity | Description                 | Designators | Product Number                                         |
| :------- | --------------------------- | ----------- | ------------------------------------------------------ |
| 1        | plcc-68 through-hole socket | U2          | [PLCC-68-AT](docs/datasheets/Adam-Tech_PLCC-68-AT.pdf) |

### Performer SE - PGA FPU

| Quantity | Description                           | Designators | Product Number |
| :------- | ------------------------------------- | ----------- | -------------- |
| 1        | pga-68 through-hole socket (optional) | U2          |                |

