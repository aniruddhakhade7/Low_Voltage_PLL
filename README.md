# Abstract
This report presents the **Low Voltage Phase-Locked Loop(PLL)** with supply noise compensation. Feedforward Ring Voltage Controlled Oscillator(VCO) with output frequency of 1500MHz and Maximum current consumption less than 1mA will be designed. As supply voltage is scaled, supply noise becomes bottleneck in VCO design. For reducing the effect of supply voltage noise in VCO, supply noise is being compared with average value of supply voltage and being feeded back to the
body terminals of Feedforward and forward path in VCO. Other PLL blocks like Phase frequency detector(PFD), Charge pump,Loop filter and Frequency divider will be designed according to mentioned target specifications.

# Introduction
For low power applications, PLL design becomes challenging task because of lower suppl voltage. As supply voltage scales down, supply voltage noise also needs to be considered while designing any block. There are many factor contributing to supply voltage noise. One simple technique is to place large capacitor between supply and ground. This requires sufficiently larger area.In the below design, we have supply noise sensing block which senses supply voltage noise and compares with the average value of supply voltage (Fig:3) and the comparison result is then feedback to Feedforward and forward path of ring VCO as shown in Fig:1 and 2. 

![PLL](https://user-images.githubusercontent.com/48211474/156175166-76aab5ba-b27f-47b7-93d9-a235cfaf3c83.png)
                                                                  Fig:1 Low Voltage PLL
                                                                
Feedforward Ring VCO consist of Forward path inverters and feedforward path inverters. When Forward path inverter becomes stronger, Oscillation frequency will incarese. When Feedforward path inverter becomes stronger, then Oscillation frequency will decrease. If Vd increases, then forward path will become weaker and hence oscillation frequency will reduce. If Vf incraeses, Feedfoward path will become weaker and Oscillation frequency will incraese.
![image](https://user-images.githubusercontent.com/48211474/156181023-d5cf4ed1-28e3-4813-a527-740eebe1ed6a.png)
Fig:2 Feedforward Ring VCO

The Noise sensing block shown in Fig  3 has two current branches. In one branch, supply noise voltage is directly affecting the voltage node Vn whereas supply noise is filtered at noise Vnavg because of capacitor filtering effect. The current in Vn branch is designed to be larger than Vnavg branch.

![image](https://user-images.githubusercontent.com/48211474/156181549-fc9dc8b7-0bf9-4bd5-8f98-517ada385e08.png)
Fig 3: Noise sensing block
