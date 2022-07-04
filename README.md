# Automation-of-HP-Adsorption-Isotherm
Automation of high-pressure adsorption isotherm intrument including more than 40 actuators, a water pump, 16 pressure transducers,16 thermocouple, a vacuum pump, a gas booster pressure control and other high pressure equipemnt.
# Table of Centent
1. [Description](#1)
2. [Code](#2)
3. [Upgrade](#3) 

<a name="1"></a>
# Description
The adsorption isotherm instrument is capable of measuring the amount of adsorbed gas, especially methane, carbon dioxide, and other gases on the rock surface of porous media, such as coal. The instrument should be capable of running the adsorption measurement automatically at high pressures (e.g. more than 4000 psi). In order to achieve this goal, a fast data acquisition system is required to control all air-operated actuators, monitor the pressure and temperature responses from the instruments and record the data from the instrument, besides performing some complicated calculations associated with PVT for the phase determination during the experiment. The following is a list of highlighted features and requirements of the developed software to handle different situations that we can encounter during the adsorption measurements: 

**Water Bath**
1. Automatically refill all water baths in case water evaporates during high-temperature experiments. The system should instantaneously check the water level using the sensor and open the valve when the water level reclines to a specific level. 
2. Automatically drain activated water baths at the end of adsorption measurement. 
3. Automatically, turn on the water pump to help drain water from water baths and stop the pump when the water is completely removed from the water baths. 
**Gas booster**
One of the most essential parts of an adsorption isotherm instrument is the gas booster. A gas booster works mechanically, when compressed air is used as a driver to elevate the pressure of the inlet gas to a higher level, e.g. 50 to 70 times higher. There is a correlation between the inlet pressure, compressed air pressure, and outlet pressure. For example, Pout=50*Pin+PS. Therefore the software should be able to adjust the pressure of compressed air and inlet gas to reach the desired outlet pressure. So,
1. The software should adjust the set pressure of the electronic gas regulator for the compressed air and inlet gas.
2. Ensure that the inlet pressure does not decline to a particular level.
3. Release the outlet pressure in case the oulet pressure exceeds the desired level.
4. Activate and deactivate the compressed air inlet to turn the gas booster ON or OFF. 

**Data Acquisition System**
1. Monitor and record the data of each senors, temperature and pressure and the status of each actuator with a particular time step (e.g. 0.5 second)
2. Display the status of the actuators and sensor feedback in the control panel for the operator.
3. Generate an error message for the operator in case the operator should modify or change the input.
4. Plot the pressure data and temperature data versus real-time.
5. Control and check possible leakage from the system and generate error messages.
6. Generate a report at the end of the measurement.
7. Self-calibration of the sensors.
8. Performing PVT calculation to prevent phase change during the experiment.
9. The system should be able to respond properly to any action causing misuse of the equipment by the operator. For example, confirm with the operator the situation that is not logically correct, such as venting the system suddenly when the pressure is very high.
10. Generating ini. file to store the calibration data and restore all calibration data prior to the measurement. 

**Pressure controlling system**
1. Switch ON or OFF the vacuum pump whenever it is needed.
2. Release the gas from the system if it approaches the max pressure rating of the equipment.
3. Adjust the pressure of the cell to the desired pressure determined by the operator. 

The following figure shows the control panel of the developed software and the graph tab of the developed software. 

![Screenshot 2022-07-03 140019](https://user-images.githubusercontent.com/108043716/177055536-4cf51f29-95cb-47ec-81a0-ccbdb336a4be.png)

Fig. 1: View of control panel of the developed software for automated HP adsoprtion Isotherm.

![image](https://user-images.githubusercontent.com/108043716/177055641-55c76485-f9ad-4bb4-8c5d-860b2c755d14.png)

Fig. 2: View of "Garph" Tab of the developed software for automated HP adsoprtion Isotherm.

<a name="2"></a>
# LabView Code
LabView computer coding software is used here to write the complicated core for the adsorption isotherm instrument. National Instrument modules are used to control more than 35 air-operated actuators, pumps, water baths, a gas booster, an air compressor, more than 32 sensors including pressure transducers and thermocouples, and other equipped devices. Figure 3 shows a part of the code involving more than 45 sub-functions.

![image](https://user-images.githubusercontent.com/108043716/177055895-a5fbcab9-d512-4559-bce5-c43ab21bd431.png)
![image](https://user-images.githubusercontent.com/108043716/177055910-36d10820-4fc1-4c0a-bdb6-dfa5a709a153.png)

Fig. 3: LabView code for the automation software including control, monitor, and store data in formatted data file. 

In order to read and convert digital data to meaningful values, you should be familiar with buffer read and write concepts. The followings are some of the highlighted parts of the software:
1. Involving more than 45 sub-functions.
2. Capable of running continuously until the measurement is done, e.g. three days of continuous data logging.
3. Capable of switching from auto-mode to manual-mode.

<a name="3"></a>
# Upgrades
This software can be upgraded to control more equipment at the same time using a stronger data acquisition system. The instrument look is shown in the following image.

![image](https://user-images.githubusercontent.com/108043716/177055811-371adc27-3d53-40c0-a0ee-0f677e146ce8.png) 

Fig. 4: HP adsorption isotherm instrument designed and constracted at PERM Inc. Instruments.

