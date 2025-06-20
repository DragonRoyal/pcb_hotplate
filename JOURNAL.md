---
title: "PCB_HOTPLATE"
author: "Aarav Singhania"
description: "A hotplate for soldering SMD components"
---

## **6/19/2025 Log 1 Research and logic of the hotplate** ##

Many traditional hotplates currently exist but ethier they are small or too expensive for larger pcb's, im designing a soldering hotplate since another project of mine as a large pcb with smd componenets and it would be easier to build one from scratch rather than spending 100+ on a hotplate. Most SMD components follow a heat curve or a tempreture profile which is most optimal for soldering the componenet onto the board. Heating it too fast or too slow can damage the component. Heres a example of a standard heating profile ![image](https://github.com/user-attachments/assets/927665aa-617d-4552-bb30-2d9ac9524f92)
With that theres a few keypoints, if I want to constantly monitor and control the tempreture of the hotplate I need a thermosister for detecting temperature, a MOFSET for turning the heating element on and off as well as a MCU as my bare minimums. To heat the pcb im going to use a 
