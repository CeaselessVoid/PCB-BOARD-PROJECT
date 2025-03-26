This section details our design choices (making reference to our roadmap). Discussed is the component lists and the choice behind the selection.Add to it how you see fit.

1. INA219.
   
This is one of the compulsory components. According to JLCPCB we have a choice between INA219AIDCNR and INA219AIDR. This was after eliminating the more expensive or rare components. This component is **extended** hence will incure an added cost to use. From my analysis i would choice the INA219AIDCNR since it is cheaper and its datasheet implies that it has the same functionality as its counterpart. Additionally, the component is smaller compared to INA219AIDR hence helps with abiding to the space constraints.

Conclusion, we can go with INA219AIDCNR (datasheet linked) which is 0.6$ (net charge of 1.2$ for the board).

2. Voltage Regulator.
   
2.1 DC to DC convertor (Boost type)

This voltage regulator will work to provide a 5V output from the 3.7V battery supply. Our choices are HT7750B, MT3540-F23 and TPS613222ADBVR. None of these were basic but in terms of cost MT3540-F23 is the cheapest. To set up the voltage regulator all three need additional components (inductors, resistors, diodes or capacitors). HT7750B achieves this while only needing three bonus components but only has a fixed 5V output. MT3540-F23 requires the most extra components but the output voltage can be configured by changing the resistor values. In terms of flexibility MT3540-F23 is a good component but it will take up more space. TPS613222ADBVR is a balanced piece(it's fixed to 5v output and the cost lies between the other two). Given that the budget takes priority we might want to consider the MT3540-F23. Another bonus is it has the 1.5A output current we desire.

2.2 LDO 

This voltage regulator will work to provide 3.3V output from the 3.7V battery supply. Our choices are AP2112K-3.3TRG1, MIC5219-3.3YM5-TR, HT7533-1(extended variant),HT7533-1(basic variant) and TPAP2112K-3.3TRG1 (all other components are extended). In terms of cost AP2112K-3.3TRG1 and HT7533-1(extended variant) are the cheeapest. To set up the voltage regulator capacitors are required. The main features to consider is the dropout voltage and the supply voltage. Using this we can eliminate HT7533-1(extended variant) and HT7533-1(basic variant) since the requirement for regulation is Vin = Vout + 2V. The choice between TPAP2112K-3.3TRG1, AP2112K-3.3TRG1 and MIC5219-3.3YM5-TR is tricky since MIC5219-3.3YM5-TR has a better PSRR but is more expensive with a higher dropout voltage. AP2112K-3.3TRG1 is the cheapest of the bunch but has a lower PSRR. For cost reasons we can eliminate MIC5219-3.3YM5-TR and the TPAP2112K-3.3TRG1. The AP2112K-3.3TRG1 was choosen since it was the most cost appropriate however the TPAP2112K-3.3TRG1 could work better since it has the highest PSRR while also being cheaper than MIC5219-3.3YM5-TR.

3. Bidirectional motor control

This will be done using H-bridge IC (s). Our choices are DRV8833PWPR, GR6205-SOP-8, and DRV8838DSGR. In terms of cost the GR6205-SOP-8 is the cheapest but it also has the the lowest output current rating at 200 mA. This means it can run the 200 mA motors but will fail for the higher current demand motors. Focusing on current rating the DRV8838DSGR is out best bet since it has a current rating of 1.8 A hence should run both motors and any other high current motors that might be brought in the future. Unfortunately, it can only drive one motor at a time hence 4 IC(s) are required which affects both cost and space. Our best an only option is the 
DRV8833PWPR which drives two motors with a current rating of 1.5 A.

4. USB PD

This will form part of the power negotiation circuit and will work with the USB-C connection to get 9v from host. Our choices are CH224K and the HUSB237-AA001-DN06R. In terms of price the HUSB237-AA001-DN06R is cheaper however the CH224K has more flexibility when it comes to configuration(does not need resistors). However, since we are only interested in basic power negotiation the cheaper option (HUSB237-AA001-DN06R) will work fine. Both have data communication functionality but it will not be utilized.

5. USB-C Connector

This will work in hand with the USB PD to negotiate for 9V from the Host. Our choices are TYPE-C 6P(073), TYPE-C 16P(073) and the TYPE-C 16P QTWT. The cheapest and simplest design was TYPE-C 6P(073). The other two seemed to offer dual connection which was not necessary for this project. Additionally, they took up more space. In conclusion, we pick the simpler solution (TYPE-C 6P(073)) since a more complex one is just redundant.

6. Load Switching IC

This will use the CRTL-EXT-load pins to provide and remove a 1A supply to a load.(we require 2 for the project). Our choices are TPS22908YZTR, RT9742GGJ5 and AP2171WG-7. In terms of price AP2171WG-7 is the cheapest. We need to consider the RDS(on) of each component since it controls the power dissipation of the IC. The TPS22908YZTR has the lowest RDS(on) however it only accepts a maximum of 3.6V. Since our board will give this section 5V we can eliminate it. Comparing the RT9742GGJ5 and AP2171WG-7 we note that the RT9742GGJ5 has a better RDS(on) but is more expensive. For this perticular design the load current is set to 1A hence the Power dissipated difference between RT9742GGJ5 and AP2171WG-7 is in the mW range hence we can settle for the cheaper component(AP2171WG-7 ). If the current requirement were to change the later would be a better choice despite its price.

