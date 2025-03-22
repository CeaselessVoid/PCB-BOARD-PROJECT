This section details our design choices (making reference to our roadmap). Discussed is the component lists and the choice behind the selection.Add to it how you see fit.

1. INA219.
   
This is one of the compulsory components. According to JLCPCB we have a choice between INA219AIDCNR and INA219AIDR. This was after eliminating the more expensive or rare components. This component is **extended** hence will incure an added cost to use. From my analysis i would choice the INA219AIDCNR since it is cheaper and its datasheet implies that it has the same functionality as its counterpart. Additionally, the component is smaller compared to INA219AIDR hence helps with abiding to the space constraints.

Conclusion, we can go with INA219AIDCNR (datasheet linked) which is 0.6$ (net charge of 1.2$ for the board).

2. Voltage Regulator.
   
2.1 DC to DC convertor (Boost type)

This voltage regulator will work to provide a 5V output from the 3.7V battery supply. Our choices are HT7750B, MT3540-F23 and TPS613222ADBVR. None of these were basic but in terms of cost MT3540-F23 is the cheapest. To set up the voltage regulator all three need additional components (inductors, resistors, diodes or capacitors). HT7750B achieves this while only needing three bonus components but only has a fixed 5V output. MT3540-F23 requires the most extra components but the output voltage can be configured by changing the resistor values. In terms of flexibility MT3540-F23 is a good component but it will take up more space. TPS613222ADBVR is a balanced piece(it's fixed to 5v output and the cost lies between the other two). Given that the budget takes priority we might want to consider the MT3540-F23. 
