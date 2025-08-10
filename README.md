# Argo

<img width="1920" height="1080" alt="Screenshot 2025-08-08 at 17 48 39" src="https://github.com/user-attachments/assets/5ceb4a81-7a7b-4c84-b6de-5be7aa7464da" />

<img width="1920" height="1010" alt="Screenshot 2025-08-08 at 18 07 07" src="https://github.com/user-attachments/assets/044bfcaa-2f4e-4551-99e2-d642546053e9" />

<img width="921" height="592" alt="Screenshot 2025-08-08 at 19 41 26" src="https://github.com/user-attachments/assets/77e72400-6a8d-4077-a443-23fb8f6aa99e" />

<img width="946" height="509" alt="Screenshot 2025-08-08 at 19 43 49" src="https://github.com/user-attachments/assets/3ed8dd86-2a15-479f-9ff9-938cbf953ff6" />

## Mainboard
The main board houses the CM5 and breaks out the most basic functionality needed.

- 2x 100pin Hirose Connectors
- 2x MIPI-DSI/CSI
- 1x Micro-HDMI
- 1x HDMI FPC connector for external break out
- 1x PCIe FPC connector, Pi 5 compatible
- 2x USB-C (One for power/flashing - USB 2.0 and one regular USB 3.0)
- Integrated BMS (BQ25895) with up to 15W output dependent on battery used.
- I2C control for BQ25895

Read more about the mainboard [here](./mainboard.md)

## Expansion Boards:

### M.2 PCIe Expansion:
- Adds an M.2 M-Key Slot for external SSD
Read more about the SSD board [here](./ssdboard.md)


### Impedance Calculations:

![Screenshot 2025-06-23 at 16 21 00](https://github.com/user-attachments/assets/02575efe-898f-4290-9d9e-e47086548d54)


## Sponsored by OSHWLab Stars and HackClub:
 &nbsp;
<img width="124" height="1000" alt="image" src="https://github.com/user-attachments/assets/e93a1d8b-093b-412c-bb61-1ad24fef76f9" />
 &nbsp;
  &nbsp;
   &nbsp;
<img width="251" height="1000" alt="image" src="https://github.com/user-attachments/assets/21c10633-868b-4a69-a2cb-da89eb62470c" />
 &nbsp;
  &nbsp;
   &nbsp;
<img width="212" height="212" alt="image" src="https://github.com/user-attachments/assets/3c6a5d8c-0add-428b-ab01-c25ad1e42543" />


Huge thanks to Bob from OSHWLab for all the support and sponsoring the PCBA! If you're a teenager interested in tech, checkout [HackClub](https://hackclub.com), huge thanks to them for covering remaining tools/materials costs.



### BOM:

| Part        | Quantity | Price    |
|-------------|----------|----------|
| Mainboard PCBA | 5        | $0.00  Paid Myself |
| SSD PCBA | 3 | $0.00 Paid myself funds redirected to soldering iron + batteries and jumper cables |
| Shipping + Taxes | 1 | $57.80 |
| [3.7V 3000mAh LiPo](https://www.aliexpress.com/item/1005006866132237.html?spm=a2g0o.cart.0.0.202b38dav2dfIE&mp=1&pdp_npi=5%40dis%21GBP%21GBP%2018.99%21GBP%2013.29%21%21GBP%2012.42%21%21%21%40211b61ae17545027136684032e8141%2112000038559144955%21ct%21UK%214887545243%21%211%210) | 1        | $25.00   |
| Raspberry Pi CM5 | | $120.00 |
| CM5 Cooler | 1 | $7.00 |
| PCIe FPC + Display FPC | 3 | $3.95 |
| Soldering iron + solder + microsoldering tips | 1 | $69 |
Note: Got sponsorship for PCB so price reduced to $61 from $350. 16GB CM5 needed due to the astro-stacking software and various other things that will be run in parallel.
