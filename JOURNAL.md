---
title: "PCB_HOTPLATE"
author: "Aarav Singhania"
description: "A hotplate for soldering SMD components"
---

## **6/19/2025 Log 1 Research and logic of the hotplate** ##

Many traditional hotplates currently exist but ethier they are small or too expensive for larger pcb's, im designing a soldering hotplate since another project of mine as a large pcb with smd componenets and it would be easier to build one from scratch rather than spending 100+ on a hotplate. Most SMD components follow a heat curve or a tempreture profile which is most optimal for soldering the componenet onto the board. Heating it too fast or too slow can damage the component. Heres a example of a standard heating profile ![image](https://github.com/user-attachments/assets/927665aa-617d-4552-bb30-2d9ac9524f92)
With that theres a few keypoints, if I want to constantly monitor and control the tempreture of the hotplate I need a thermosister for detecting temperature, a MOFSET for turning the heating element on and off as well as a MCU as my bare minimums. To heat the pcb im going to wrap nichrome wire and copper plates for the top. For the top I could choose between copper or aluminum but after some research I chose copper since it was almost 70% at conducting heat and the cost compared to aluminum was not substational enough to warrent a switch. The cheapest options I could find were 2 copper plates so im going to connect them with thermal paste and screws. I chose nichrome wire since it can reach a very high mac tempreture and I can coil the wire for better heat distribution

**Time spent: 3 hours**

## ** 6/22/2025 Log 2 CAD and more research on different parts ** ##
My hotplate will have a big heating area in order which can fit up to 400mm by 400mm PCB's, in order to reach consistant heating over the heating area im going to have to have nichrome wire routed in close proximity to each other, but I still need to have hardstops to prevent accidentaL shorts. Im going to have 2 copper plates connected by a thin solder joint. For the wires I constructed a box and made traces of wires run through it to ensure the entire box area is properly covered. ![image](https://github.com/user-attachments/assets/1eee4ec4-4db9-4b56-8cb7-dd96ca0f0193) and then I ran a linear pattern through it ![image](https://github.com/user-attachments/assets/4b08c178-1042-4036-9108-bfa9c95667ef)
I want the heating part to be "seperate" from the enclosure so it does not accidently melt it, so I added standooffs which seperated the distance as well as fans to cool the plate after heating. I also added a THT screen for displaying tempeture profiles as well as 2 buttons for switching/selecting between the different profiles.
![image](https://github.com/user-attachments/assets/28e59456-79ae-4242-b615-e92abef160b3)
**Time spent 5 hours**

## **6/25/2025 Log 3 PCB and new heating element progress ** ##
Through lots of research I landed on the conclusion my current heating option is not that robust or reliable, I have to seperate the wire from the plate to prevent shorts and I would have to run AC mains through the wires which is a big safety hazard. A option I was considering earlier was having PCB hotplates but I didn't initially want to do it since they will eventually burn out after 10-20 reflows and none of the ones currently made have reflow profiles. But I'd rather get a version working then have nothing so for now im going to deal with the limited lifetime problem later, and have a seperate pcb which controls the "hot plate pcb" through a MCU and thermosister. I wanted to make sure that the wires had the sweet spot of resistance I needed in order to provide around 12v-24v and still "only" provide 5-15 amps of current.
![IMG_6463](https://github.com/user-attachments/assets/82657db7-8d4b-490f-997e-537d14304a85)
^ Some calculations I did to figure out thermistor logic as well as heat increase (Joules) with different Voltages and Current values. I needed to make sure the wires had enough resistance so I wouldnt need to provide a unfeasibly low voltage like a few milivolts with a few amps so I also spread out my track to cover up the entire area of the pcb. To calculate how much resistance each track had I used this online calculator ![image](https://github.com/user-attachments/assets/1789c866-b41c-4d7d-a95d-b3a1c6ca0fe1) Initially my traces were 1.27mm wide but that gave me 12.7Ohms which would require too much current to properlly heat up the pcb, to decrease the voltage I made the traces wider which also decreased how long the wires would need to run for. I ended up with 4mm wire which had a total length of almost 400 inches!
![Screenshot 2025-06-25 002943](https://github.com/user-attachments/assets/2c966fd8-9a4e-4cf8-ae98-756b63a1b63a)![Screenshot 2025-06-25 002954](https://github.com/user-attachments/assets/d66a1dc3-eada-4daf-b1ce-64b6adc51a86)

**Time spent 4 hours**

## **6/26/2025 Log 4 Update CAD to be polished** ##
One thing I noticed was my cad was a bit basic and rudimentry, I wanted to build a more polished and profesional case of my hot place. So I completely redesigned it. 
It will now hav ea angled screen and control panel and a more lightweight frame. 
![Screenshot 2025-06-25 231238](https://github.com/user-attachments/assets/00b4401d-e169-47d4-88cd-5a5c5a3c3b98) I designed the sketch for it and extruded it as long as added holes to help with ventilation and airflow from the 2 fans underneath the case. ![Screenshot 2025-06-25 231309](https://github.com/user-attachments/assets/bb849fcc-3212-44bf-875d-2d74157922ce) I then focused on improving the case a bit more by adding fillets and rounding the edges in order to make it more clean. 
![Screenshot 2025-06-25 231320](https://github.com/user-attachments/assets/d700c9e4-a53e-4727-b8d2-5aef36a6be69) and I then I just finished the assembly and added all my parts, the pcb with the oled and buttons, 2 fans underneath the case, the heating pcb and 4 standoffs![image](https://github.com/user-attachments/assets/46bd34d3-122e-4514-a6c9-bc1910ca7524)
**Time spent 5 hours**

## **6/27/2025 Log 5 Master PCB work** ##
Since I already made my pcb heater I made my master pcb in which all the power would go into and it would control the entire machine. I would have 2 wires which connect to the pcb heater sheet with a MCU and thermosistor to detect tempreture. I would have 2 buttons for selecting and picking which reflow curve to follow as well as a TFT screen showing the tempreture curve. ![image](https://github.com/user-attachments/assets/809cc774-008e-43c4-a03d-1f615189867b) I worked on the schematic and learned about how a thermosistor works and how to convert the resistance it gives into current ![Thermistor-Reading-Circuit](https://github.com/user-attachments/assets/bc890471-7977-41fa-9c8b-f62b129ac68f) I also created a few symbols such as the buck converter ![Screenshot 2025-06-13 165949](https://github.com/user-attachments/assets/d6800ad6-e26e-4641-b7f9-e9e15f8440ef) I then created the layout for the actual board which was relatively straight forward and I routed it. 
![image](https://github.com/user-attachments/assets/901192a3-5d5f-4c15-953d-a5997cee69be)![image](https://github.com/user-attachments/assets/03a5acd4-5da8-427a-b3db-904dee4ecafc)
**Time spent 3 hours**







