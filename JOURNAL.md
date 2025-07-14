---
title: Icarus
author: Muhammad Azlan Shah
description: Opensource battery powered CM5 carrier board.
created_at: "2025-06-25"
---

June 20th:

Initial Roadmapping, component selection and formfactor decisions.

![image](https://github.com/user-attachments/assets/6859e266-0c45-494b-8c0a-7ee2ce87619d)

Decided on formfactor similar to Waveshare Nano series due to nice compact formfactor.

June 22nd:

Exploring TPS61088 based boost converter system for fixed 5V battery power:

<img width="1125" height="1042" alt="image" src="https://github.com/user-attachments/assets/07e71390-31d5-4639-a88e-ec29dccbe8dc" />

Runs in conjuction with loadsharing battery charging IC.

June 24th

Scrapped TPS61088, most LiPos can't safely discharge more than 3-5A unless its a 18650 or similar at 1S so its ideal to use built in boost converter of BQ25895 for up to 5V @ 3.1A for the CM5.

<img width="1090" height="806" alt="image" src="https://github.com/user-attachments/assets/262943d9-c38b-4b7f-88c0-e836158d3dec" />

Completed schematic above.

June 30th:

Began layout after completing remaining schematics based on CM5 IO Board schematics for basic functionality.

Using a 4 Layer stack up as SIG/PWR : GND : GND : SIG/PWR

July 3rd:

Turns out 4 layers will not be sufficient due to small board size and power routing. Moving to 6 layer stack up as SIG/PWR : GND : SIG/PWR : PWR : GND : SIG/PWR

Got sanity check on TI Forum for BQ25895 layout and schematic for more confidence.

<img width="1125" height="2144" alt="image" src="https://github.com/user-attachments/assets/f8b3c005-5418-47d6-b58b-dc88ccaa67b2" />

