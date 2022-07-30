# Troubleshooting
 Game and Watch Backup - Troubleshooting  

## Restoring original flash fails
> Success, your device should be running the original firmware again!

Problem: After running `5_backup.sh` I'm shown the message above, but after power cycling the system, instead of the original firmware, I got blinking white blocks on the screen. What am I doing wrong?

Solution: The success message is a lie :P Run script 5 again and it should be fine. If not, try again a few more times, if you still get the same flashing screen your connection is no good. Connectivity is just the beginning. Use short wires, reduce adapter speeds and re-flow solder joints.

## Game and Watch Retro Go - Troubleshooting

### Chunk 0 failed
> Flashing chunk 0 failed... power cycle unit and retry? (y/n)

Problem: Attempting to flash the G&W fails with the message above.

Solution: With the USB-C cable disconnected from the G&W, press and hold the power button. Re-connect the USB-C cable and continue holding the power button while starting the appropriate `make` script over again.

### Flash overflowed
> /usr/lib/gcc/arm-none-eabi/9.2.1/../../../arm-none-eabi/bin/ld: region `FLASH' overflowed by 4612 bytes

Problem: There isn't enough available storage space for the files you're trying to write to the system.

Solution: Reduce the amount of files, or if the overflow is small enough, you can try using the `LARGE_FLASH=1` command on themake line.

If you're using a 2MB, 4MB, 8MB, or 16MB chip, you must use the LARGE_FLASH=1 command. For larger chips such as a 32MB or 64MB, you'll need to specify the size using EXTFLASH_SIZE=67108864as well as use the 32-Bit addressing flag FLASH_ADDRESS_BITS_32=1.

### WRPERR
> Error: wait_flash_op_queue, WRPERR detected

Problem: This is a write protection error. Unlocking must have failed.

Solution: Locate your `game-and-watch-flashloader` folder and run `./scripts/flashloader.sh $ADAPTER backups/flash_backup.bin` to restore the original backup and unlock again. Where $ADAPTER is the name of your debugger (stlink, jlink, rpi).

### ROMS
> Error: wait_flash_op_queue, WRPERR detected

Problem: Flashed ROMS not showing up?

Solution: ROM files MUST be uncompressed. So NO .zip or.7z files!
