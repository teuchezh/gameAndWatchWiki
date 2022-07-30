# FAQ

## STORAGE

> Q: How many NES games can I put on the Game & Watch's stock chip?

A: At the time of writing, if you're using the GUI branch of Retro-Go you're limited to 246.6kB. This works out to be exactly 10 NES games, each exactly 24.6kB in size (0.16kB unused). This is because the GUI and Savestates will use up the remainder of the flash storage available. UPDATE: I was recently able to fit 23 NES Games onto a stock device, using a method [discussed here](https://www.reddit.com/r/GameAndWatchMods/comments/ksucsu/trick_to_fit_more_roms_on_the_stock_1mb_flash/).

If you're not using the GUI, you can currently only load (1) ROM. This can be somewhere between 512kB and 640kB. Notice I said ROM, and not games? This is because you can make a single ROM that contains multiple ROMs/Games.

This doesn't include the use of compression which is now available.

> Q: How can I tell if all my games will fit on my unit?

A: Run the `make size` command in the terminal from within the game-and-watch-retro-go folder. Pro Tip: You should specify the size of your flash: Example: `make size EXTFLASH_SIZE_MB=64` but to avoid those annoying overflow errors that still don't tell you how much space you're using, just double it!

Example: `make size EXTFLASH_SIZE_MB=128` Now you should see how much space you're using. (Don't forget to run `make clean` in between and to set EXTFLASH_SIZE_MB back to the same size as your chip! `EXTFLASH_SIZE_MB=64`)

## GUI

> Q: What is the maximum filename length to fit the screen when using `retro-go` ?

A: 40 Characters. Anything more will show off screen.

## REGION

> Q: Every time I attempt a flash I get a openocd command not found error. Exporting the openocd path doesn’t help. I use openocd for other parts of the process without issues. Am I doing something wrong here?

A: I haven't personally seen any regional issues when running games, whether they're NTSC, PAL or NTSC-J, they should work fine. See the [Compatibility List](https://www.reddit.com/r/GameAndWatchMods/wiki/rom-compatibility) for known issues.

## OPENOCD

> Q: Every time I attempt a flash I get a openocd command not found error. Exporting the openocd path doesn’t help. I use openocd for other parts of the process without issues. Am I doing something wrong here?

A: This is a common issue new users run into and it's simple to fix. [See my post here for more information](https://www.reddit.com/r/GameAndWatchMods/comments/p7pcc6/opensource_custom_firmware_project_now_available/hav5pa8?utm_source=share&utm_medium=web2x&context=3)

## FACTORY RESET

> Q: How can I Reset my Game & Watch Systems to Factory Settings?

A: Follow the directions below..

Applies to the 2020 Game & Watch: Super Mario Bros. or 2021 Game & Watch: The Legend of Zelda
Important: Once this process is done, all save data will be deleted and cannot be recovered unless you have backed it up correctly using retro-go.
Complete thee following steps:
On the Game & Watch press and hold simultaneously the following buttons for four seconds: PAUSE/SET Button, Up (on the +Control Pad), and the POWER Button.