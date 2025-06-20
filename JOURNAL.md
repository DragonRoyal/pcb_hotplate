---
title: "PCB_HOTPLATE"
author: "Aarav Singhania"
description: "A hotplate for soldering SMD components"
---

## **6/19/2025 Log 1 Research and logic of the hotplate** ##

Many traditional hotplates currently exist but ethier they are small or too expensive for larger pcb's, im designing a soldering hotplate since another project of mine as a large pcb with smd componenets and it would be easier to build one from scratch rather than spending 100+ on a hotplate. Most SMD components follow a heat curve or a tempreture profile which is most optimal for soldering the componenet onto the board. Heating it too fast or too slow can damage the component. Heres a example of a standard heating profile ![image](https://github.com/user-attachments/assets/927665aa-617d-4552-bb30-2d9ac9524f92)
With that theres a few keypoints, if I want to constantly monitor and control the tempreture of the hotplate I need a thermosister for detecting temperature, a MOFSET for turning the heating element on and off as well as a MCU as my bare minimums. To heat the pcb im going to wrap nichrome wire and copper plates for the top. For the top I could choose between copper or aluminum but after some research I chose copper since it was almost 70% at conducting heat and the cost compared to aluminum was not substational enough to warrent a switch. The cheapest options I could find were 2 copper plates so im going to connect them with thermal paste and screws. I chose nichrome wire since it can reach a very high mac tempreture and I can coil the wire for better heat distribution

** Time spent: 3 hours**
