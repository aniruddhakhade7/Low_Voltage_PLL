# Abstract
This report presents the **Low Voltage Phase-Locked Loop(PLL)** with supply noise compensation. Feedforward Ring Voltage Controlled Oscillator(VCO) with output frequency of 1500MHz and Maximum current consumption less than 1mA will be designed. As supply voltage is scaled, supply noise becomes bottleneck in VCO design. For reducing the effect of supply voltage noise in VCO, supply noise is being compared with average value of supply voltage and being feeded back to the
body terminals of Feedforward and forward path in VCO. Other PLL blocks like Phase frequency detector(PFD), Charge pump,Loop filter and Frequency divider will be designed according to mentioned target specifications.

# Introduction
For low power applications, PLL design becomes challenging task because of lower suppl voltage. As supply voltage scales down, supply voltage noise also needs to be considered while designing any block. There are many factor contributing to supply voltage noise. One simple technique is to place large capacitor between supply and ground. This requires sufficiently larger area.In the below design, we have supply noise sensing block which senses supply voltage noise and compares with the average value of supply voltage (Fig:3) and the comparison result is then feedback to Feedforward and forward path of ring VCO as shown in Fig:1 and 2. 

![PLL](https://user-images.githubusercontent.com/48211474/156175166-76aab5ba-b27f-47b7-93d9-a235cfaf3c83.png)
                                                                  Fig:1 Low Voltage PLL
 
# Feedforward Ring VCO 
Feedforward Ring VCO consist of Forward path inverters and feedforward path inverters. When Forward path inverter becomes stronger, Oscillation frequency will increase. When Feedforward path inverter becomes stronger, then Oscillation frequency will decrease. If Vd increases, then forward path will become weaker (due to body effect) and hence oscillation frequency will reduce.Similarly, If Vf increases, Feedfoward path will become weaker and Oscillation frequency will increase. Vd and Vf are generated from Supply noise sensing block. 
![image](https://user-images.githubusercontent.com/48211474/156181023-d5cf4ed1-28e3-4813-a527-740eebe1ed6a.png)
Fig:2 Feedforward Ring VCO

The Noise sensing block shown in Fig  3 has two current branches. In one branch, supply noise voltage is directly affecting the voltage node Vn whereas supply noise is filtered at noise Vnavg because of capacitor filtering effect. The current in Vn branch is designed to be larger than Vnavg branch. Vd will be **A(Vn-Vnavg)**** whereas Vf will be **A(Vnavg-Vn)** where A is gain of inverting amplifier shown in Fig:3

![image](https://user-images.githubusercontent.com/48211474/156181549-fc9dc8b7-0bf9-4bd5-8f98-517ada385e08.png)
Fig 3: Noise sensing block

If we have supply noise of sinusoidal nature (Assumed noise to be sinusoid for illustration but it will be random), then Vn and Vnavg will be sinusoid and filtred DC  respectively. This value is then given to inverting amplifier which will then generate Vd and Vf which are complementary to each other. When supply noise increases,Vn will increase hence Vd will increase and Vf will decrease. When supply noise increases, Oscillation frequency will increase when there is no noise sensing block. Noise sensing block will work in opposite direction and reduce frequency proportional to supply noise. Therefore Supply Noise effect will be reduced.
![image](https://user-images.githubusercontent.com/48211474/156192027-315459eb-2783-411b-ab08-d3367bee7428.png)
Fig 4: Noise sensing functioning

# Feedforward Ring VCO design
VCO is designed as shown in Fig: 5. It has feedforward and feedback inverter as shown in Fig 6 and 7.
![image](https://user-images.githubusercontent.com/48211474/156193952-0d8d8d6a-8b9b-40c5-934c-fbc323572df2.png) <br/>
                                        Fig 5: Feedforward Ring VCO schematics

![image](https://user-images.githubusercontent.com/48211474/156194136-0147c5da-8110-4c25-a404-7b670fc3078e.png) <br/>
                                        Fig 6: Feedforward path inverter <br/>
                                        
                                        
![image](https://user-images.githubusercontent.com/48211474/156194218-1d044628-dd81-4053-8baf-e42f0908488b.png)<br/>
                                        Fig 7: Feedback path inverter <br/>
            
 Noise sensing is designed accordingly as per explained in previous section. <br/>
 ![image](https://user-images.githubusercontent.com/48211474/156195259-03ef90cd-437a-45bb-9504-640dad45a7c1.png)<br/>
                                       Fig 8: Noise Sensing block
                                       
   ![image](https://user-images.githubusercontent.com/48211474/156195438-7371c52e-a684-4acc-970c-c5cce27699af.png) <br/>
                                       Fig 9: Inverting Amplifier
VCO along with supply noise sensing block is as follows: <br/>
![image](https://user-images.githubusercontent.com/48211474/156195872-b2415a05-fdcf-48bb-9f3b-845e5c66ec3b.png) <br/>
                                       Fig 10: VCO along with noise sensing block


