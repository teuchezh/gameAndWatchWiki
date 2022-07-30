# Display

FPC Connector
This describes the connection of the FPC connector towards the STM32:
```
GND
    VCC (1.8)
VCC (3.3)
    GND
54 PB15 SPI2_MOSI/I2S2_SDO
    31 PA7 LCD_VSYNC
63 PC6 LCD_HSYNC
    53 PB14 LCD_CLK
43 PE13 LCD_DE
    52 PB13 SPI2_SCK/I2S2_CK
51 PB12 General purpose output
    GND
45 PE15 LCD_R7
    67 PA8 LCD_R6
68 PA9 LCD_R5
    70 PA11 LCD_R4
34 PB0 LCD_R3
    78 PC10 LCD_R2
84 PD3 LCD_G7
    64 PC7 LCD_G6
47 PB11 LCD_G5
    46 PB10 LCD_G4
66 PC9 LCD_G3
    15 PC0 LCD_G2
83 PD2 LCD_B7
    95 PB8 LCD_B6
91 PB5 LCD_B5
    69 PA10 LCD_B4
57 PD10 LCD_B3
    87 PD6 LCD_B2
55 PD8 General purpose output
    GND
GND
```


SPI Startup Data
This is needed to bring up the display, sent in bursts of two bytes with 100ms pause in between. 0880 6e80 8080 6800 d000 1b00 e000 6a80 8000 1480


[Source](https://github.com/ghidraninja/game-and-watch-hacking/wiki/Display)