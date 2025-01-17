# Tsar Hardware
Hardware for the Test Stand Automation and Regulation project that runs [PSAS' Liquid Fuel Engine Test Stand](https://github.com/psas/liquid-engine-test-stand)

The TSAR system controls the test stand at a safe distance with several safety features in place. The system monitors the pressure, temperature, and valve states of the system. For automation software and controls see the [tsar software repo](https://github.com/psas/tsar-software). 

The OSGC Final UTEAP Report contains more detailed information and can be found [here](https://docs.google.com/document/d/1x4pjh9ZbApyyvRd1HysukK7K5CVWpYE1/edit?usp=sharing&ouid=116385191421445654590&rtpof=true&sd=true).

## Tsar Hardware System Architecture Block Diagrams

Below you can see the levels of block diagrams for the whole system,

### V -1

![sys_arch](https://github.com/psas/tsar-hardware/blob/master/images/TSAR_SA_BDneg1.png?raw=true)

### V 0

![sys_arch](https://github.com/psas/tsar-hardware/blob/master/images/TSAR_SA_BD0.png?raw=true)

### V 1

![sys_arch](https://github.com/psas/tsar-hardware/blob/master/images/TSAR%20System%20Architecture.png?raw=true)

## Systems Within the Repo

Within this repo there are several subsystems.

![sys_arch](https://github.com/psas/tsar-hardware/blob/master/images/TSAR%20System%20Architecture_repo.png?raw=true)

### [LOTO](https://github.com/psas/tsar-hardware/tree/master/LOTO)

The LOTO Repo is the Lock-Out Tag-Out subsystem.

This system prevents the test stand from being powered while key-holders are past the safety line. 


### [Thrust Plate Amplifier](https://github.com/psas/tsar-hardware/tree/master/Thrust%20Plate%20Amplifier)

The Thrust Plate Amplifier amplifies the thrust plate signal.


### [Actuator Controller](https://github.com/psas/tsar-hardware/tree/master/actuator-controller)

This board communicates with the BB-AI over UART and controls the valves. The processor is a STM32F0 using a Nucleo-board. 

For more information on the software for this board please see [Actuator Controller Code, Firmware](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Firmware) and [Actuator Controller Code, Test](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Test)

### [Tsar Sensor Front End](https://github.com/psas/tsar-hardware/tree/master/tsar_SensorFrontEnd)

This board collects the data from all of the sensors (temperature, pressure, thrust plate) and conditions the signals to send to the Marionette. 

### [Valve Indicator](https://github.com/psas/tsar-hardware/tree/master/valve_indicator)

This board collects the valve position data and compares it to the expected valve state. If there is an error it will display a code over LEDs to indicate which valve is misbehaving. 

For more information on the software for this board please see [Valve Indicator Code](https://github.com/psas/tsar-software/tree/master/valve_indicator)
