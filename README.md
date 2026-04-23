<p align="center">
  <img src="images/main_cad.png" alt="DIY 3D Space Mouse" width="800">
</p>

# DIY_Space_Mouse

A simple, affordable, and open-source 3D mouse. Designed to make 3D navigation accessible to everyone without the premium price tag.

## 3D Printing

Every structural part of this mouse is 3D printable. I used standard PLA with default settings, and it works great. You can pick any color that fits your desk setup.

* **Material:** PLA (or PETG if you prefer).
* **Settings:** Default/Standard settings are fine.
* **Optional:** If you want the LEDs to look a bit more polished, print the diffuser in clear PLA. If you aren't a fan of the lighting, you can just leave that part out entirely.

## Assembly Guide

Putting the mouse together is quite simple. You will just need a few pieces of hardware to get started.

### Hardware Needed
* **Heat-Set Inserts:** 16 x M3 x 4mm
* **M3 Screws:** 10 x 16mm and 5 x 12mm
* **M2 Screws:** 1 x 4mm
* **Magnets:** 6 x (6mm x 3mm)

### Steps to Assemble
1. **The Spring:** The top part of the mouse screws directly into the spring. The spring is parametric, so if the movement doesn't feel quite right to you, you can adjust the files and re-print it.
   <p align="center"><img src="images/spring.png" alt="Spring Assembly" width="600"></p>

2. **Magnets:** Seat the magnets into the top housing. These are essential for the sensors to track movement.
3. **The Base:** Place the PCB into the bottom part of the housing. It is secured with screws from the bottom.
   <p align="center"><img src="images/pcb_mount.png" alt="PCB Mounting" width="600"></p>

4. **The Brain:** Plug the XIAO RP2040 into the stacked PCB. Make sure everything is seated firmly.
   <p align="center"><img src="images/pcb_stack.png" alt="PCB Stack" width="600"></p>

5. **Closing up:** Screw the bottom plate on from the underside. If you’re using the clear diffuser, make sure it’s in place before you close everything up.

---

## The PCB

The electronics are based on the XIAO RP2040. While you can have this board professionally assembled by a service like JLCPCB, I’m planning to assemble my own using a hot plate (or heat gun) and some solder paste.

### Design & Schematics
* **Schematic:**
  <p align="center"><img src="images/schematics.png" alt="Schematic" width="700"></p>

* **Board Layout:**
  <p align="center"><img src="images/PCB.png" alt="PCB Layout" width="700"></p>

---

## Firmware

The firmware is currently untested. The goal is for the device to spoof the hardware ID of a 3Dconnexion device so it works seamlessly with their existing software. It uses the same HID protocols as any other 3d mouse, found from google.

* **Tools:** Everything was written in VS Code.
* **How to Upload:** Use PlatformIO to flash the firmware onto the XIAO RP2040.

Simply plug in your device, open the project in VS Code, and use the PlatformIO "Upload" button to get it running.

---

### BOM
|Name                       |Purpose                                       |Quantity|Total Cost (USD)|Link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |Distributor|
|---------------------------|----------------------------------------------|--------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|Electronic Componets       |To assemble PCB                               |10      |16.97           |https://www.lcsc.com/                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |LCSC       |
|6mm x 3mm Neodymium Magnets|Used for tracking mouse head                  |3       |6.98            |https://www.amazon.com/JUNAN-Neodymium-Cylinder-Magnetic-Whiteboard/dp/B08TQMV921/ref=sr_1_6?crid=2SAFS6PA2Q742&dib=eyJ2IjoiMSJ9.zC10nqy2DxrcGJY-lUdIl2P2S_xuiVRJWM5_B52ieExA5uJIT5wJ6iVgxzf1Gj4A1cPeA2j3dNxCiM0qDue7ZHYuXmdOW1bWt2ngpSdE8eXU0VhZR7BONlLakJa9nqIaWjOr3fafcKZS1nex2iqkTRaOmoOjkYMhn1_0eRxokXAjliBMX3B540qvwxU_CBjyFojkOkmzNL2v96ACZdFRQmjcqvyCeJhAUzj6B5_XYzQ.pVqaHqfQ0ZfdTJvCwn87ajgwYdjuH_mf_106Mp5Nz8Y&dib_tag=se&keywords=6mm+x+3mm+Neodymium+Magnets&qid=1776780341&sprefix=6mm+x+3mm+neodymium+magnets%2Caps%2C213&sr=8-6                             |Amazon     |
|Seeed Studio XIAO RP2040   |To take magnet positions and send it to laptop|1       |9.99            |https://www.amazon.com/Microcontroller-Dual-Core-MicroPython-CircuitPython-Interfaces/dp/B09NNVNW7M/ref=sr_1_1?crid=2JIMESFTJTFIW&dib=eyJ2IjoiMSJ9.Hxs3jCHqokIXwzSfDn6Q0_2Z9xo6z7IQzP1BJ3N_LFoRv3IxZfzavjqKufbRi5yM3hMuaSGGcuhiXy6oVl1IsZlwMlwzvXZHsFFUUcxGNmMj82PKt5hK4yFMrJ2f_QmioEkoztDLV0ZBr_GEfA8kAhYQhyh9M8TJ6pcMngnhpRE-pgNpFDoxbWeyzvz97m0BEIlwbZM0pAlpjP2HrEFDwSsZcxcEhdBUsTXg78w3VCM.SpQmdXhVqTn3eRD2UhhPMyZoWSpMFGZgeAfdalCWaCk&dib_tag=se&keywords=Seeed%2BStudio%2BXIAO%2BRP2040&qid=1776780229&sprefix=seeed%2Bstudio%2Bxiao%2Brp2040%2Caps%2C235&sr=8-1&th=1|Amazon     |


