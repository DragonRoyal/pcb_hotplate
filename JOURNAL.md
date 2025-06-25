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

## **6/25/2024 Log 3 PCB and new heating element progress ** ##
THrough lots of research I landed on the conclusion my current heating option is not that robust or reliable, I have to seperate the wire from the plate to prevent shorts and I would have to run AC mains through the wires which is a big safety hazard. A option I was considering earlier was having PCB hotplates but I didn't initially want to do it since they will eventually burn out after 10-20 reflows and none of the ones currently made have reflow profiles. But I'd rather get a version working then have nothing so for now im going to deal with the limited lifetime problem later, and have a seperate pcb which controls the "hot plate pcb" through a MCU and thermosister. I wanted to make sure that the wires had the sweet spot of resistance I needed in order to provide around 12v-24v and still "only" provide 5-15 amps of current.
^ Some calculations I did to figure out thermistor logic as well as heat increase (Joules) with different Voltages and Current values. I needed to make sure the wires had enough resistance so I wouldnt need to provide a unfeasibly low voltage like a few milivolts with a few amps so I also spread out my track to cover up the entire area of the pcb. To calculate how much resistance each track had I used this online calculator ![image](https://github.com/user-attachments/assets/1789c866-b41c-4d7d-a95d-b3a1c6ca0fe1) Initially my traces were 1.27mm wide but that gave me 12.7Ohms which would require too much current to properlly heat up the pcb, to decrease the voltage I made the traces wider which also decreased how long the wires would need to run for. I ended up with 4mm wire which had a total length of almost 400 inches!
![Screenshot 2025-06-25 002943](https://github.com/user-attachments/assets/2c966fd8-9a4e-4cf8-ae98-756b63a1b63a)![Screenshot 2025-06-25 002954](https://github.com/user-attachments/assets/d66a1dc3-eada-4daf-b1ce-64b6adc51a86)

**Time spent 4 hours**




