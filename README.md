# PCB-BOARD-PROJECT
Currently we still need to flesh out our design in terms of component choice, back up designs and the actual design.
Below is all the data we have currently(the requirements of the project) :
1. Operate up to 4 motors bidirectionally with the pins available to you (listed in the power pinout table). You will need to control 2x brushed DC motors which could each draw 200mA at the highest voltage of a 1S1P battery (the battery is further specified in the battery section).The other 2x motors are for the auxiliary connection and need to operate 500mA each.
2. Place an INA219 for monitoring the battery on the I2C Bus and configure it correctly with respect to the hardware (cannot have BOTH A0 AND A1 on GND)
3. Charge the battery from the 9V input pin (listed in the power pinout table).
4. Have two charging modes for a higher and lower charging current for the battery (200mA, and approximately 600mA ±100mA from the battery perspective.
5. Integrate USB C and get 9V out of the USB Host
6. Provide 2x External Load Switching at 1A each (High Side connected to your 5V)
7. Provide a 3V3 5% accuracy (300mA max) and 5V Out 5% accuracy (1.5A max)
8. Provide an ON/OFF switch. OFF state: battery draw <30uA. ON state: can provide your robot peak current of 2A. The switch needs to shut down 5V and 3V3.

So far we have locked in the components INA219 and possiblely the H-bridge. This will need to be deducted from our budget once we fin a suitable vendor.(As it stands we have $56.5 for the components).
Other points:
1. The board solution should be 82 x 60 (mm)
2. We cannot excede the budget
3. Deadline is the 28th of March (we should try to finalize well before this)
4. All components sourced from JLCPCB

Future things to add here: 
1. We need to add the schemetic and PCB design
2. Possible links to the datasheets we used for an easier time during report writing
3. Any computations we do(again mainly for reference)

https://cdn-shop.adafruit.com/datasheets/ina219.pdf - INA219
