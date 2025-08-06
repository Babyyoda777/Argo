# Argo

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
  
![Screenshot 2025-06-29 at 16 38 10](https://github.com/user-attachments/assets/39c998c6-869e-438a-ada8-2e50c2cf9fd6)
![Screenshot 2025-06-29 at 16 39 02](https://github.com/user-attachments/assets/b91c2f8f-2672-4234-bbd9-1b4975fe4b93)

Read more about the mainboard [here](./mainboard.md)

## Expansion Boards:

### M.2 PCIe Expansion:
- Adds an M.2 M-Key Slot for external SSD
Read more about the SSD board [here](./ssdboard.md)


### Impedance Calculations:

![Screenshot 2025-06-23 at 16 21 00](https://github.com/user-attachments/assets/02575efe-898f-4290-9d9e-e47086548d54)



### BOM:

| Part        | Quantity | Price    |
|-------------|----------|----------|
| Mainboard PCBA | 5        | $61.00   |
| SSD PCBA | 3 | $128.00 |
| [3.7V 3000mAh LiPo](https://www.aliexpress.com/item/1005006866132237.html?spm=a2g0o.cart.0.0.202b38dav2dfIE&mp=1&pdp_npi=5%40dis%21GBP%21GBP%2018.99%21GBP%2013.29%21%21GBP%2012.42%21%21%21%40211b61ae17545027136684032e8141%2112000038559144955%21ct%21UK%214887545243%21%211%210) | 1        | $25.00   |
| [Raspberry Pi CM5 16GB](https://www.digikey.co.uk/en/products/detail/raspberry-pi/SC1607/25805578) | 1 | $130.00 |


Note: Got sponsorship for PCB so price reduced to $61 from $350. 16GB CM5 needed due to the astro-stacking software and various other things that will be run in parallel.
