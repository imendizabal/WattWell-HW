# Aim of the project

The main goal of the project is to develop an open source inverter (Hardware and Software).  
This inverter should exist in different configurations: Monophasic (1-ph) and threephasic (3-ph). However, it is planned to be able to add a DC/DC converter for solar applications for example.

An important part of the project is to be able to work with different types of switching components (IGBT/MOSFET). Nowadays, we often see that inverters are replaced after 10 years but they keep working or some faulty inverters that are not easily repared because the design is not modular or easy to fix.

Then, the goal is to design an Open Source inverter that is modular to be easy to be fixed and flexible enough to have differents functionalities (batteries/PV/...)

The project will be divided into different "workpackages" or sub projects, on Hardware side we have:

1. Control board: development of the main control board able to get the measurements, generate PWM's, ... This board embeds the main mcu.
2. Driver board: interface between the control board and power switch (IGBT's/Mosfet's)
3. Power circuit: power circuit of the inverter (LCL filter, DC bus, ...)

on the firmware side (main mcu based on STM32G434):

1. Low level drivers
2. Basics functionalities (bootloader, debug uart, pll,...)
3. Advanced functionalities (power management, MPPT, state machine)

# Expected functionalities

- Being able (and allowed) to be connected to the European grid
- MPPT for solar panels (with DC/DC)
- Battery connection
- Communication capabilities (serial,...)
- Working in islanding mode (offgrid)

# 1. main control board:

The main control board will be able to measure:
1.  3AC voltages (max 400V) - ADC min 14bits
2.  2DC voltages (max 1500V) -ADC min 14bits
3.  4AC/DC current measurement - ADC min 14bits
4.  Temperature measurement

The main control board will have the following interface:
1.  2X UART(1X to RS485; 1X to USB)
2.  1xSPI
3.  2xI2C
4.  1xCAN
5.  6X PWM's
6.  6X DO's
7.  6X DI's
8.  6X AI'S (temp from IGBT/Mos)

Other functions:
1.  Debug LED
2.  RTC (supercap based)
3.  Additionnal ROM (TBD)
4.  Watchdog
5.  Power supply for IGBT's/Mosfets
   
