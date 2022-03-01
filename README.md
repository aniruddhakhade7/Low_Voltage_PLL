# Introduction
For low power applications, PLL design becomes challenging task because of lower suppl voltage. As supply voltage scales down, supply voltage noise also needs to be considered while designing any block. There are many factor contributing to supply voltage noise. One simple technique is to place large capacitor between supply and ground. This requires sufficiently larger area.In the discussed design [1], we have supply noise sensing block which senses supply voltage noise and compares with the average value of supply voltage (F ig : 3) and the comparison result is then feedback to Feedforward and forward path of ring VCO as shown in Fig:1 and 2.

![PLL](https://user-images.githubusercontent.com/48211474/156175166-76aab5ba-b27f-47b7-93d9-a235cfaf3c83.png)
