---
title: Icarus
author: Muhammad Azlan Shah
description: Opensource battery powered CM5 carrier board.
created_at: "2025-06-25"
total time spent: 62 hours
---

# June 20th:

Initial Roadmapping, component selection and formfactor decisions.

![image](https://github.com/user-attachments/assets/6859e266-0c45-494b-8c0a-7ee2ce87619d)

Decided on formfactor similar to Waveshare Nano series due to nice compact formfactor.

Time Spent: 3 hours

# June 22nd:

Exploring TPS61088 based boost converter system for fixed 5V battery power:

<img width="1125" height="1042" alt="image" src="https://github.com/user-attachments/assets/07e71390-31d5-4639-a88e-ec29dccbe8dc" />

Runs in conjuction with loadsharing battery charging IC. Main idea is that most TI battery chargers have an internal fet that can pass through around 6A of continuous discharging current from the battery. This means, boosted to 5V, you can generally get 4-5A so around meeting the Pi 5 requirements but depending on how charged the battery is. This exceeds the usual 5V 3A limit that the integrated OTG boost that some chargers support can provide. Still need to consider whether this is actually worth it as the TPS61088 takes a large amount of board space.


Time Spent: 5 hours

# June 24th

Scrapped TPS61088, most LiPos can't safely discharge more than 3-5A unless its a 18650 or similar at 1S so its ideal to use built in boost converter of BQ25895 for up to 5V @ 3.1A for the CM5. This comes off the back of the CM5 datasheet power requirements section which states that during normal operation it uses 900mA. Additional testing from Jeff Geerling shows the absolute max power draw (when under stress) by an overcloked CM5 was around 8W. This leaves around 7.5W for remaining functions which fits almost perfectly with the 2.5W output for the USB port and 5W needed for rhe PCIe connection. Thanks Jeff!

<img width="1090" height="806" alt="image" src="https://github.com/user-attachments/assets/262943d9-c38b-4b7f-88c0-e836158d3dec" />

Completed schematic above.

Time spent: 3 days

# June 30th:

Began layout after completing remaining schematics based on CM5 IO Board schematics for basic functionality.

Using a 4 Layer stack up as SIG/PWR : GND : GND : SIG/PWR

Time spent: 8 hours

# July 3rd:

Turns out 4 layers will not be sufficient due to small board size and power routing. Moving to 6 layer stack up as SIG/PWR : GND : SIG/PWR : PWR : GND : SIG/PWR

Got sanity check on TI Forum for BQ25895 layout and schematic for more confidence.

<img width="1125" height="2144" alt="image" src="https://github.com/user-attachments/assets/f8b3c005-5418-47d6-b58b-dc88ccaa67b2" />

Time Spent: 16 hours (complete rerouting needed).


# July 4th:

Further look into USB-C and USB 3.0 turns out to get CM5 to have a USB-C 3.0 port rather than a simple USB-A 3.0 port you need and SS Mux to manage the reversible connector and its need for double the RX and TX superspeed lines. Luckily the regular USB 2.0 D+ and D- lines don't really need anything as the traces are relatively shot so redriver is optional and its probably ok.

<img width="1193" height="446" alt="Screenshot 2025-08-01 at 19 41 24" src="https://github.com/user-attachments/assets/0d23850a-5f44-4a00-a5e3-1df6d240f569" />

Time spent: 4 hours

# July 5th:

Worked on finding a suitable small battery connector. Decided to use a Molex backplane connector as it can handle up to 6A which is around 24W max and 18W minimum if pushing full 6A through so should be more than enough to handle CM5 with a high discharge LiPo/Li-ion.

<img width="148" height="83" alt="Screenshot 2025-08-01 at 19 44 30" src="https://github.com/user-attachments/assets/4987487e-443f-4d48-b946-726b2489932b" />

Time spent: 2 hours

# July 6th:

Rerouted HDMI differential pairs for slightly cleaner look. Also increased trace width for power supply to micro-HDMI port just to be safe: 

<img width="712" height="423" alt="Screenshot 2025-08-01 at 19 51 54" src="https://github.com/user-attachments/assets/e7d687ca-3a4b-437b-ac96-1f9e4656546c" />

Time spent: 1 hour

# July 7th:

Worked on breaking out som GPIO as dedicated I2C and SPI lines. Also added connector for CM5 fan as these things can run hot and thermal throttle:

<img width="440" height="310" alt="Screenshot 2025-08-01 at 19 53 24" src="https://github.com/user-attachments/assets/bee41fa3-dc23-4782-9ad3-18778ac4ecd7" />

Time spent: 1 hour


# July 8th:

Redid layout for BQ25895 again. Focus on minimising overheating and some concern for EMI. Considered using resistor array for 10k resistors however its more expensive to use an array and functionally not significant so left as is. New routing:

<img width="597" height="452" alt="Screenshot 2025-08-01 at 19 57 56" src="https://github.com/user-attachments/assets/7517f159-bf27-4049-9073-4087a0188c0c" />

Time spent: 2 hours

# August 4th:

Sent for production but had issue spotted on PCB. Turns out length matching on inner layer was a bit too close so was at risk of short circuit. Got it fixed so should be good to go!

<img width="1288" height="947" alt="Screenshot 2025-08-04 at 14 05 05" src="https://github.com/user-attachments/assets/224c3fef-1d43-4f7a-9cfc-165f96021e2b" />

Time spent: 1 hour

# August 5th:

Started work on SSD add-on. This board is a miniaturised version of the official M.2 HAT+ but with minor changes to work purely off the PCIe flex cable without requiring external 5V. As such it consumes a max of 5W but also means the SSD being used will need to be low power. 

<img width="652" height="515" alt="image" src="https://github.com/user-attachments/assets/640820b8-2859-4f89-8d68-7971ebeeef3d" />

From above, the board also uses a much thinner profile M.2 Connector and screw mounts, as such only single sided M.2 NVMe SSDs will work. Whilst double sided ones will work, it may be difficult to get them flush to the board but that awaits testing.

The reason for this choice is to allow for a battery to be stacking underneath this board. Together with the main board, the total dimensions from a bird's eye view is 85mm x 55mm which includes a 5mm gap between the two, which will be used for routing of PCIe FPC cable.

IMPORTANT NOTE: The FPC connectors used are both double sided contacts, this is to allow flexibility of board placement and also which FPC cable is used.

Time spent: 3 hours
