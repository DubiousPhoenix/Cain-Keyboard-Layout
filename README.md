# Cain-Keyboard-Layout
Keyboard layout designed for Keebio Iris Rev 4 board. 2 Encoders, 54 Keys, and 2 Layers.

This layout is configured to work with QMK's MSYS and with the Keebio Iris Rev 4 keyboard. This might work with rev 5 and 6 but I wouldn't know.

Install Instructions -
*Compile the Hex/ Change the Keybindings*
1 - download the *QMK_MSYS Setup* from here "https://msys.qmk.fm"
2 - download the *cain* zip file from "https://github.com/DubiousPhoenix/Cain-Keyboard-Layout/releases/tag/1.0"
3 - Run QMK_MSYS Setup.exe & select "install drivers". Then finish installing.
4 - Find where you installed QMK_MSYS to and open "QMK MSYS" (should be a SHORTCUT)
5 - type "qmk setup" then press "Enter"
5.5 - here, qmk should ask you if you'd like to install firmware to your "C:\Users\{You}". Type "y" and press "Enter".
6 - In your Windows Explorer, navigate to "C:\Users\{You}\qmk_firmware\keyboards\keebio\iris"
7 - Extract the *cain* folder from the *cain.zip* you downloaded earlier.
7.5 - If you want to tweak the keybindings this is when you do it. Via the *keymap.c* file. That's all on you and I won't walkthrough that. But I hope "https://beta.docs.qmk.fm/using-qmk/simple-keycodes/keycodes_basic" can help you out.
8 - Move that *cain* folder into the keymaps folder
9 - In *QMK MSYS* type "qmk compile -kb keebio/iris/rev4 -km cain" and press enter. (You can replace rev4 with whatever revision your board is but I don't guarentee it will work.)
10 - *QMK MSYS* will now compile the keyboard layout into a hex file that by default can be located in "C:\Users\{You}\qmk_firmware". That hex file is used in the *Hex Flashing* section. You can now close QMK MSYS as it won't be used from here on out.

*Hex Flashing*
This is the process you should use if you have my exact keyboard layout. Which most of you don't but this is something you'll be doing regardless of if you are building your own hex or using mine.
1 - Download the *keebio_iris_rev4_cain.hex* file from "https://github.com/DubiousPhoenix/Cain-Keyboard-Layout/releases/tag/1.0"
2 - Download *qmk_toolbox.exe* from "https://github.com/qmk/qmk_toolbox/releases/tag/0.1.1" (if there's a newer release grab that instead I guess.)
3 - Open *qmk_toolbox.exe*
4 - In the section that says Local File, you'll see this box that says click open or drag to window to select file. Do so. Click "Open" and select the *keebio_iris_rev4_cain.hex* file or drag the *keebio_iris_rev4_cain.hex* file you downloaded from earlier into that box.
5 - Time to flash. Unplug the TRRS Cable (the aux cord thing that connects the keyboards).
6 - One half of your keyboard should still be plugged in via usb c. On the back of THAT keyboard, press the small button called reset. On your monitor, you should see that QMK Toolbox says Atmel DFU device connected. Good.
7 - Now click the button that says "Flash" on the right side of QMK Toolbox's window. You should see more text pop up saying something like "Attemtping to flash, please don't remove device". After it's done, it will say "Atmel DFU device disconnected". Good. (If for some reason you don't see success on this part, I don't know what could be wrong. It's possible an issue with your particular board and you might need to burn even more money to buy a new one. I can't help you with that.)
8 - Unplug the USB-C cord from your keyboard. Now plug it into the OTHER half of the keyboard. Remember, the TRRS Cable (Aux Cord) should STILL be unplugged from the other board right now.
9 - Repeat Step 6. On the back of your keyboard press the reset button.
10 - Once you see QMK Toolbox say Atmel DFU device connected you're ready to once again, click "Flash".
11 - Once again, it will finish flashing and disconnect the Atmel device.
12 - Now you can switch your USB-C Cable back to the primary half of your keyboard and reconnect the TRRS Cable (Aux Cord). You can close everything else and the keyboard should be good to go.
