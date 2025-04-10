# OpenBook

## Diagrama

![image](https://github.com/user-attachments/assets/889bf782-7415-48fd-a0eb-9f9a92b12cbc)

## Bill Of Materials

| Componenta | Datasheet | Model |
|------------|-----------|-------|
| ESP32-C6-WROOM-1-N8 | [Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-c6_datasheet_en.pdf) | [Model](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda) |
| W25Q512JVEIQ | [Datasheet](https://www.winbond.com/resource-files/W25Q512JV%20RevI%2005132020%20Plus.pdf) | [Model](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda) |
| DS3231SN# | [Datasheet](https://datasheets.maximintegrated.com/en/ds/DS3231.pdf) | [Model](https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/?ref=eda) |
| MAX17048G+T10 | [Datasheet](https://datasheets.maximintegrated.com/en/ds/MAX17048-MAX17049.pdf) | [Model](https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda) |
| BME688 | [Datasheet](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bme688-ds000.pdf) | [Model](https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home) |
| MCP73831 | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20001984g.pdf) | [Model](https://www.snapeda.com/parts/MCP73831T-2ACI-OT/Microchip/view-part/?ref=eda) |
| BD5229G-TR | [Datasheet](https://fscdn.rohm.com/en/products/databook/datasheet/ic/power/voltage_detector/bd52xxg-e.pdf) | [Model](https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor) |
| USBLC6-2SC6Y | [Datasheet](https://www.st.com/resource/en/datasheet/usblc6-2.pdf) | [Model](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda) |
| 112A-TAAR-R03 | [Datasheet](https://www.attend.com.tw/sites/default/files/2022-05/112A-TAAR-R03.pdf) | [Model](https://www.snapeda.com/parts/112A-TAAR-R03/ATTEND/view-part/?ref=eda) |
| FH34SRJ-24S-0.5SH | [Datasheet](https://www.hirose.com/product/document?clcode=CL0684-0832-7-99&productname=FH34SRJ-24S-0.5SH(99)&series=FH34&documenttype=Catalog&lang=en&documentid=D49681_en) | [Model](https://www.snapeda.com/parts/FH34SRJ-24S-0.5SH(99)/Hirose/view-part/?ref=eda) |
| DMG2305UX-7 | [Datasheet](https://www.diodes.com/assets/Datasheets/DMG2305UX.pdf) | [Model](https://www.snapeda.com/parts/DMG2305UX-7/Diodes%20Inc./view-part/?ref=eda) |
| SI1308EDL-T1-GE3 | [Datasheet](https://www.vishay.com/docs/68732/si1308edl.pdf) | [Model](https://www.snapeda.com/parts/SI1308EDL-T1-GE3/Vishay+Siliconix/view-part/?ref=snap) |
| MBR0530 | [Datasheet](https://www.onsemi.com/pdf/datasheet/mbr0520lt1-d.pdf) | [Model](https://www.snapeda.com/parts/MBR0530/Onsemi/view-part/?ref=eda) |
| PGB1010603MR | [Datasheet](https://www.littelfuse.com/media?resourcetype=datasheets&itemid=3d1e98b7-4d37-463c-9380-c56c83b11c3c&filename=littelfuse-pulseguard-pgb1) | [Model](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda) |
| XC6220A331MR-G | [Datasheet](https://www.torexsemi.com/file/xc6220/XC6220.pdf) | [Model](https://www.snapeda.com/parts/XC6220A331MR-G/Torex+Semiconductor/view-part/?ref=eda) |
| EVQPUJ02K | [Datasheet](https://industrial.panasonic.com/cdbs/www-data/pdf/ATV0000/ATV0000CE5.pdf) | [Model](https://www.snapeda.com/parts/EVQPUJ02K/Panasonic/view-part/?ref=eda) |
| GDEH0154D67 | [Datasheet](https://www.good-display.com/companyfile/203.html) | [Model](https://www.good-display.com/product/207.html) |
| CPH3225A | [Datasheet](https://www.sii.co.jp/en/quartz/files/2021/03/CPH3225A_E.pdf) | [Model](https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/?ref=eda) |


## Functionalitatea hardware

Proiectul foloseste un ESP32-C6 ca microcontroller central, cu urmatoarele componente principale:

1. **Display E-Ink (GDEH0154D67)** - afisaj de 1.54" cu 200x200 pixeli conectat prin SPI, perfect pentru afisarea datelor cu consum minim de energie, deoarece consuma curent doar la actualizarea ecranului.

2. **Memorie Flash externa (W25Q512JVEIQ)** - 64MB de stocare SPI pentru date, configuratii si loguri cand dispozitivul este in modul deep sleep.

3. **Senzor de mediu (BME688)** - masoara temperatura, umiditatea, presiunea atmosferica si calitatea aerului, conectat prin I2C.

4. **Ceas RTC (DS3231)** - mentine ora exacta chiar si cand dispozitivul este oprit, conectat prin I2C.

5. **Sistem de alimentare**: 
   - Baterie LiPo 3.7V
   - Circuit de incarcare (MCP73831)
   - Monitor baterie (MAX17048G)
   - Regulator LDO 3.3V (XC6220A331MR-G)
   - Convertor 5V (pentru componente care necesita 5V)

6. **Interfata USB-C** - pentru incarcare si comunicatii, cu protectie ESD (USBLC6-2SC6Y).

7. **Butoane tactile (EVQPUJ02K)** - 3 butoane pentru interfata utilizator.

8. **Slot card microSD** - pentru stocarea datelor in volum mare.


## Descrierea pinilor ESP32-C6

- **GPIO1-2**: Magistrala I2C principala pentru conectarea senzorilor si RTC-ului DS3231, fiind pinii hardware dedicati pentru I2C.

- **GPIO3**: Pin RESET pentru reinitializarea sistemului.

- **GPIO4**: SS_SD pentru selectarea cardului microSD, parte a interfetei SPI dedicate cardului.

- **GPIO5**: Pin EPD_DC pentru controlul displayului E-Ink (Data/Command).

- **GPIO6**: Pin SPI SCK (clock) utilizat pentru comunicatia cu displayul si alte dispozitive SPI.

- **GPIO7**: Pin MOSI pentru transferul de date spre dispozitivele SPI.

- **GPIO8-9**: Pini pentru interfata RTC (32kHz si INT_RTC), utilizati pentru wake-up si sincronizare.

- **GPIO10**: Pin pentru controlul FLASH_CS, selectand memoria flash externa.

- **GPIO11**: Pin EPD_CS pentru selectarea displayului E-Ink.

- **GPIO12**: Pin EPD_RST pentru resetarea displayului E-Ink.

- **GPIO13-14**: Pini USB_D- si USB_D+ pentru comunicatia USB.

- **GPIO15**: Pin IO/BOOT pentru controlul bootarii sistemului.

- **GPIO16-18**: Pini pentru controlul displayului e-ink (EPD_3V3, EPD_BUSY).

- **GPIO19-21**: Pini SCL, SDA pentru o secunda interfata I2C folosita pentru comunicatie cu senzorii adaugati.

- **GPIO22-23**: Pini pentru control I/O general si semnale de control pentru display.

- **GPIO26-28**: Pini pentru LED-uri de status si controlul modulului.

## Poze
![Screenshot 2025-04-06 211106](https://github.com/user-attachments/assets/a85283d7-237c-4e88-8208-186757081327)



