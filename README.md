# Abstract
This report presents the **Low Voltage Phase-Locked Loop(PLL)** with supply noise compensation. Feedforward Ring Voltage Controlled Oscillator(VCO) with output frequency of 1500MHz and Maximum current consumption less than 1mA will be designed. As supply voltage is scaled, supply noise becomes bottleneck in VCO design. For reducing the effect of supply voltage noise in VCO, supply noise is being compared with average value of supply voltage and being feeded back to the
body terminals of Feedforward and forward path in VCO. Other PLL blocks like Phase frequency detector(PFD), Charge pump,Loop filter and Frequency divider will be designed according to mentioned target specifications.

# Introduction
For low power applications, PLL design becomes challenging task because of lower suppl voltage. As supply voltage scales down, supply voltage noise also needs to be considered while designing any block. There are many factor contributing to supply voltage noise. One simple technique is to place large capacitor between supply and ground. This requires sufficiently larger area.In the discussed design [1], we have supply noise sensing block which senses supply voltage noise and compares with the average value of supply voltage (F ig : 3) and the comparison result is then feedback to Feedforward and forward path of ring VCO as shown in Fig:1 and 2.

![PLL](https://user-images.githubusercontent.com/48211474/156175166-76aab5ba-b27f-47b7-93d9-a235cfaf3c83.png)
Fig:1 Low Voltage PLL
