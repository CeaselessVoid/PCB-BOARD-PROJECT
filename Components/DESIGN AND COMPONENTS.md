This section details our design choices (making reference to our roadmap). Discussed is the component lists and the choice behind the selection.Add to it how you see fit.

1. INA219.
   
This is one of the compulsory components. According to JLCPCB we have a choice between INA219AIDCNR and INA219AIDR. This was after eliminating the more expensive or rare components. This component is **extended** hence will incure an added cost to use. From my analysis i would choice the INA219AIDCNR since it is cheaper and its datasheet implies that it has the same functionality as its counterpart. Additionally, the component is smaller compared to INA219AIDR hence helps with abiding to the space constraints.

Conclusion, we can go with INA219AIDCNR (datasheet linked) which is 0.6$ (net charge of 1.2$ for the board).

2. Voltage Regulator.
   
2.1 DC to DC convertor (Boost type)

This voltage regulator will work to provide a 5V output from the 3.7V battery supply. Our choices are HT7750B, MT3540-F23 and TPS613222ADBVR. None of these were basic but in terms of cost MT3540-F23 is the cheapest. To set up the voltage regulator all three need additional components (inductors, resistors, diodes or capacitors). HT7750B achieves this while only needing three bonus components but only has a fixed 5V output. MT3540-F23 requires the most extra components but the output voltage can be configured by changing the resistor values. In terms of flexibility MT3540-F23 is a good component but it will take up more space. TPS613222ADBVR is a balanced piece(it's fixed to 5v output and the cost lies between the other two). Given that the budget takes priority we might want to consider the MT3540-F23. Another bonus is it has the 1.5A output current we desire.

2.2 LDO 

This voltage regulator will work to provide 3.3V output from the 3.7V battery supply. Our choices are AP2112K-3.3TRG1, MIC5219-3.3YM5-TR, HT7533-1(extended variant),HT7533-1(basic variant) and TPAP2112K-3.3TRG1 (all other components are extended). In terms of cost AP2112K-3.3TRG1 and HT7533-1(extended variant) are the cheeapest. To set up the voltage regulator capacitors are required. The main features to consider is the dropout voltage and the supply voltage. Using this we can eliminate HT7533-1(extended variant) and HT7533-1(basic variant) since the requirement for regulation is Vin = Vout + 2V. The choice between TPAP2112K-3.3TRG1, AP2112K-3.3TRG1 and MIC5219-3.3YM5-TR is tricky since MIC5219-3.3YM5-TR has a better PSRR but is more expensive with a higher dropout voltage. AP2112K-3.3TRG1 is the cheapest of the bunch but has a lower PSRR. For cost reasons we can eliminate MIC5219-3.3YM5-TR and the TPAP2112K-3.3TRG1. The AP2112K-3.3TRG1 was choosen since it was the most cost appropriate however the TPAP2112K-3.3TRG1 could work better since it has the highest PSRR whill also being cheaper than MIC5219-3.3YM5-TR.

3. Bidirectional motor control

This will be done using H-bridge IC (s). Our choices are DRV8833PWPR, GR6205-SOP-8, and DRV8838DSGR. In terms of cost the GR6205-SOP-8 is the cheapest but it also has the the lowest output current rating at 200 mA. This means it can run the 200 mA motors but will fail for the higher current demand motors. Focusing on current rating the DRV8838DSGR is out best bet since it has a current rating of 1.8 A hence should run both motors and any other high current motors that might be brought in the future. Unfortunately, it can only drive one motor at a time hence 4 IC(s) are required which affects both cost and space. Our best an only option is the 
DRV8833PWPR which drives two motors with a current rating of 1.5 A.

