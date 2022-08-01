# Upgrading the Game & Watch Storage

[Click HERE for a WARNING before you buy your chip!](https://www.reddit.com/r/GameAndWatchMods/comments/oppfs8/warning_for_those_of_you_buying_flash_chips/)

In order to upgrade the storage in the Nintendo Game & Watch you'll need to replace the external storage. Preferably with a chip from the "Stock Firmware" Compatibility list below . This is a small 1.8V (1.65-2V), 8 pin serial flash chip (MX25U8035F) in what's called a 8 Pin SOP or WSOP-8 Package.

Before you replace the storage though, make sure you have a backup of current chip and stock firmware. Make a few and compare their checksums to ensure you're getting a proper dump.

You can follow the [instructions here](https://github.com/ghidraninja/game-and-watch-backup) by stacksmashing if you haven't already done this part. You can of course simply attach a clip to the chip, and dump the firmware that way, so long as your programmer supports 1.8V chips (The CH341A for example DOES NOT support such chips and can damage the system and should not be used without the proper 1.8v add-on board).

Now that you've got a backup, you'll need to remove the logic board from the Game & Watch completely and carefully de-solder the stock external storage chip using a hot air station or a soldering iron. It's important to take great care when doing this, as you can easily damage the board traces and other components in the process, rendering your Game & Watch useless. If you've never done this before, please watch some video tutorials on YouTube and do some tests on some scrap hardware first.

Some solder wick and flux will go along way in both the chips removal, and when soldering in the replacement. Make sure when placing the new chip in place that you match the pins up correctly, aligning the small dot on the chip with the pin with the arrow pointing to it on the board (Pin 1). Once you've soldered in the replacement chip, use a multi-meter to check the connections for issues. You can view the [boards schematic here](https://github.com/Upcycle-Electronics/game-and-watch-hardware) if you need help. Assuming you have no issues, you can now restore the original backup you created using script 5 (5_restore.sh)

## Stock & Custom Firmware Compatible

The following NOR flash chips are compatible with the stock firmware that ships on the device. These chips are recommended as they require no additional modifications.

| Manufacture | Size           | Voltage | Socket | Model              | Link                                                           |           |
| ----------- | -------------- | ------- | ------ | ------------------ | -------------------------------------------------------------- | --------- |
| Macronix    | 64Mbit (8MB)   | 1.8V    | 8SOP   | MX25U6432FM2I02    | [BUY NOW](https://www.findchips.com/search/MX25U6432FM2I02)    | IN STOCK! |
| Macronix    | 128Mbit (16MB) | 1.8V    | 8SOP   | MX25U12835FM2I-10G | [BUY NOW](https://www.findchips.com/search/MX25U12835FM2I-10G) | IN STOCK! |
| Macronix    | 128Mbit (16MB) | 1.8V    | 8SOP   | MX25U12832FM2I02   | [BUY NOW](https://www.findchips.com/search/MX25U12832FM2I02)   | IN STOCK! |
| Macronix    | 256Mbit (32MB) | 1.8V    | *8WSON | MX25U25635FZ2I-10G | [BUY NOW](https://www.findchips.com/search/MX25U25635FZ2I-10G) | IN STOCK! |
| Macronix    | 512Mbit (64MB) | 1.8V    | *8WSON | MX25U51245GZ4I00   | [BUY NOW](https://www.findchips.com/search/MX25U51245GZ4I00)   | IN STOCK! |
*8WSON chips are difficult to solder, Hot Air Station highly recommended!

## Custom Firmware Compatible

The following flash chips do not work with the stock firmware. You should avoid using these chips if possible. If you have to pick one, for the moment I would recommend the IS25WP128F-JBLE.

| Manufacture                 | Size           | Voltage | Socket | Model           | Link                                                         |           |
| --------------------------- | -------------- | ------- | ------ | --------------- | ------------------------------------------------------------ | --------- |
| Integrated Silicon Solution | 128Mbit (16MB) | 1.8V    | 8SOP   | IS25WP128F-JBLE | [BUY NOW](https://www.findchips.com/search/IS25WP128F-JBLE)  | IN STOCK! |
| WINBOND                     | 128Mbit (16MB) | 1.8V    | 8SOP   | W25Q128FWSIG    | [BUY NOW](https://www.findchips.com/search/MX25U51245GZ4I00) |

## INCOMPATIBLE CHIPS

We discourage / advice against using the Cypress/Infineon large flash chips (S25HS512T, S25FS512S), Because they use a 256kB fixed erase size, they will be a huge pain to support properly. Eventually, we might have good support for them but not right now.


| Manufacture      | Size | Voltage | Socket | Model     | Link |
| ---------------- | ---- | ------- | ------ | --------- | ---- |
| Cypress/Infineon | n/a  | 1.8V    | WSON8  | S25HS512T | n/a  |
| Cypress/Infineon | n/a  | 1.8V    | WSON8  | S25FS512S | n/a  |
*Support for chips from the following manufactures will come at a later date *

+ MT
+ Giga Device (GD)
+ AT

Find more supplies here:
https://www.reddit.com/r/GameAndWatchMods/wiki/supplies

## Need Help Soldering in your new chip? or modding in General?

Checkout your local [Hack Spaces](https://en.wikipedia.org/wiki/Hackerspace) and [find one near you](https://wiki.hackerspaces.org/List_of_Hacker_Spaces)!

