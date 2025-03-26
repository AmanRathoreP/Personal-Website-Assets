---
title: GSU Automation
date: "2024-10-05"
description: In this project, my main goal was to automate the gas sensing unit(GSU) which was initially controlled by a PLC.
tags:
  - chemistry
  - software
  - electronics
  - lab
categories:
  - inst
image: gsu.png
---

## Objective
- Automate the process of controlling gas(s) flow along with reading the data from mass flow meter of
M3030A
- Make our solution scalable enough so that we can add more functionality to it via other sensors, modules, etc.
- Make a user friendly UI in-order to easily control the system(s)
- Design the solution in a way that if things go wrong we can easily revert to last working stage(In a nutshell don't mess with PLC)

## Solutions that we came up with

### Re-program the PLC to read data from a microcontroller and then take actions accordingly
#### Problems
- Zero experience with PLCs
- According to Swastik Corporation's operator we can't read or take the backup of the already uploaded ladder structure on DW7S-M8-AI4-R8-AO4-CS
- We don't have PLC's ladder structure and HMI code
- We don't have an extra PLC to tinker with

### Replace the PLC entirely with a microcontroller
#### Problems
- Lack of documentation for M3030A
- M3030A takes input as the voltage in range of 0V to 5V, in-order to finely control the gas flow we'll be required to use an external DAC as well as an external ADC(to get gas flow meter data)
- M3030A costs ₹25K(ebay), so if things go wrong...
- Lack of expertise in highly sensitive control systems. If readings are abnormal with just the un-noticeable magnitude we won't even know that there is a problem.