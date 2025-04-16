Biro Anya-Andreea 332CA

# OpenBook

## Diagrama bloc
![Diagrama bloc](./Images/block-diagram.jpg)

## BOM
| Componenta              | Descriere                             | Sursa | Datasheet |
|-------------------------|----------------------------------------|--------|-----------|
| ESP32-C6-WROOM-1-N8     | Multiprotocol Module ESP32             |[Mouser](https://ro.mouser.com/ProductDetail/Espressif-Systems/ESP32-C6-WROOM-1-N8?qs=8Wlm6%252BaMh8ST02Gmwp74cw%3D%3D)|[Datasheet](https://ro.mouser.com/datasheet/2/891/Espressif_ESP32_C6_WROOM_1__Datasheet_V0_1_PRELIMI-3239987.pdf)|
| USB4110-GF-A            | USB Type C Connector                   |[Mouser](https://ro.mouser.com/ProductDetail/GCT/USB4110-GF-A?qs=KUoIvG%2F9IlYiZvIXQjyJeA%3D%3D)|[Datasheet](https://ro.mouser.com/datasheet/2/837/GCT_USB4110_Product_Drawing___20k_cycles-3455479.pdf)|
| 112A-TAAR-R03           | Micro SD Card Socket                   |[Comet](https://store.comet.srl.ro/Catalogue/Product/43497/)|[Datasheet](https://store.comet.bg/download-file.php?id=27596)|
| BME680                  | Air Quality Sensor                     |[Mouser](https://ro.mouser.com/ProductDetail/Bosch-Sensortec/BME680?qs=v271MhAjFHjo0yA%2FC4OnDQ%3D%3D)|[Datasheet](https://ro.mouser.com/datasheet/2/783/BST_BME680_DS001-1509608.pdf)|
| DS3231SN#               | Real Time Clock                        |[Mouser](https://ro.mouser.com/ProductDetail/700-DS3231SN%23)|[Datasheet](https://ro.mouser.com/datasheet/2/609/DS3231-3421123.pdf)|
| EVQ-P4MB3K              | Tactile Switch                         |[Mouser](https://ro.mouser.com/ProductDetail/Panasonic/EVQ-P4MB3K?qs=0aNVN3t2tDvlcmyoDZjvlA%3D%3D)|[Datasheet](https://4donline.ihs.com/images/VipMasterIC/IC/PANA/PANA-S-A0000771493/PANA-S-A0000771493-1.pdf?hkey=CECEF36DEECDED6468708AAF2E19C0C6)|
| MCP73831-2ACI/MC        | Battery Charge Controller              |[Mouser](https://ro.mouser.com/ProductDetail/579-MCP73831-2ACI-MC)|[Datasheet](https://ro.mouser.com/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf)|
| MAX17048G+T10           | Battery Management                     |[Mouser](https://ro.mouser.com/ProductDetail/Analog-Devices-Maxim-Integrated/MAX17048G%2bT10?qs=D7PJwyCwLAoGnnn8jEPRBQ%3D%3D)|[Datasheet](https://ro.mouser.com/datasheet/2/609/MAX17048_MAX17049-3469099.pdf)|
| FH34SRJ-24S-0.5SH(99)   | EPD Connector                          |[Mouser]()|[Datasheet]()|
| PRT-14417               | Qwiic JST Connector                    |[Mouser]()|[Datasheet]()|
| W25Q512JVEIQ            | NOR Flash                              |[Mouser]()|[Datasheet]()|
| R0402                   | Resistor                               |[Mouser]()|[Datasheet]()|
| B72540T0300K062         | Varistor                               |[Mouser]()|[Datasheet]()|
| C0402C475K8PACTU        | Capacitor                              |[Mouser]()|[Datasheet]()|
| T491B107M006AT          | Tantalum Capacitor                     |[Mouser]()|[Datasheet]()|
| USBLC6-2SC6Y            | ESD Protection Diode                   |[Mouser]()|[Datasheet]()|
| PGB1010603MR            | ESD Protection Diode                   |[Mouser]()|[Datasheet]()|
| SD0805S020S1R0          | Schottky Diode                         |[Mouser]()|[Datasheet]()|
| MBR0530-TP              | Small Signal Schottky Diode            |[Mouser]()|[Datasheet]()|
| LSM0603472V             | Single Color LED                       |[Mouser]()|[Datasheet]()|
| DMG2305UX-7             | MOSFET P-Ch                            |[Mouser]()|[Datasheet]()|
| SI1308EDL-T1-GE3        | MOSFET N-Ch                            |[Mouser]()|[Datasheet]()|
| CPH3225A                | Supercapacitor                         |[Mouser]()|[Datasheet]()|
| 744043680               | SMD Inductor                           |[Mouser]()|[Datasheet]()|
| BD5229G-TR              | Voltage Detector                       |[Mouser]()|[Datasheet]()|
| XC6220A331MR-G          | LDO Voltage Regulator                  |[Mouser]()|[Datasheet]()|

## Descriere functionalitate hardware
Proiectul **OpenBook** are ca scop dezvoltarea unui dispozitiv portabil de afișare a informațiilor, cu consum redus de energie, conectivitate Wi-Fi și senzori de mediu.

### Module și interfețe utilizate

- **ESP32-C6** – Microcontroller central cu suport pentru Wi-Fi și BLE. Rulează logica principală și gestionează comunicația cu toate perifericele.
- **BME680** – Senzor pentru calitatea aerului, conectat prin magistrala I2C.
- **DS3231SN** – Ceas de timp real (RTC), conectat I2C.
- **W25Q512JVEIQ** – Memorie NOR Flash SPI pentru stocare de date suplimentară.
- **MAX17048** – Circuit de monitorizare a bateriei, interfață I2C.
- **MCP73831** – Controler de încărcare baterie LiPo.
- **Conector EPD + ecran E-Ink** – Conectat SPI, pentru afișare cu consum redus.
- **Slot microSD** – SPI, pentru citire/scriere fișiere.
- **Buton tactile (EVQ-P4MB3K)** – Intrare digitală, GPIO.
- **Conector USB-C (USB4110-GF-A)** – Încărcare și interfață serială.
- **LED + rezistor + MOSFET** – Indicatoare vizuale, controlate de GPIO.
- **Diodă Schottky, varistori, ESD diode** – Protecție electrică.

### Comunicație și consum

- I2C: folosit pentru BME680, RTC, Battery Gauge
- SPI: utilizat pentru ecranul E-Ink, memoria Flash și SD card
- GPIO: pentru butoane, LED-uri, MOSFET-uri
- UART: pentru debugging via USB
- Estimare consum: 
    - **Mod Activ:** ~220 mA @ 3.3V → ~727 mW  
    - **Mod Sleep:** ~27 µA @ 3.3V → ~0.089 mW  
    - **Autonomie estimată:** ~14 zile cu baterie Li-Po 1200mAh


## Mapare Pini ESP32-C6

| Componentă              | Pin ESP32-C6         | Interfață   | Motiv |
|-------------------------|----------------------|-------------|-------|
| BME680                  | GPIO4 (SDA), GPIO5 (SCL) | I2C      | Comun cu alți senzori, ușor de multiplexat |
| DS3231SN                | GPIO4, GPIO5         | I2C         | Același bus cu BME680 |
| E-Ink Display           | GPIO10, GPIO11, ...  | SPI         | Viteză mare de transfer |
| SD Card                 | GPIO10, GPIO11, ...  | SPI         | Partajat cu E-Ink, dar exclusiv accesat |
| MAX17048                | GPIO4, GPIO5         | I2C         | Comun pe bus |
| MCP73831                | GPIO22 (STAT)        | GPIO        | Monitorizare stare încărcare |
| Buton                  | GPIO12               | GPIO        | Interacțiune utilizator |
| LED                    | GPIO13               | GPIO        | Semnalizare |
| UART (debug)           | GPIO20 (TX), GPIO21 (RX) | UART    | Serial debugging |


## Alte Informații Relevante
- Fișiere schematice și PCB disponibile în `/Hardware`
- Fișiere 3D disponibile în `/Mechanical`
- Randări ale PCB-ului:
![PCB_2D](./Images/2D_PCB.png)
![PCB_3D](./Images/3D_PCB.png)
- Randări ale dispozitivului:
![Carcasă](./Images/device_cover.png)
![Ecran](./Images/device_top.png)
![Mufe](./Images/device_bottom.png)
![Interior](./Images/interior_full.png)
