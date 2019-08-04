# MacOS-Z370N-WiFi

Good news guys! I've managed to boot with F12 bios. It is easier than you think. Here is a simple step by step guide.

1. Make a boot USB flash drive with your current EFI folder.
2. Download [bootx64.efi](https://d.pr/f/0oeThZ) and copy it to EFI/Boot/.
This is some kind of alternative bootloader that starts with the command line. Here we will modify hidden BIOS settings.

3. Update BIOS to F12 (only F12!)
4. Reboot and hold F12 to boot from your USB Flash drive. Now you should see this command line.
5. Now enter

`setup_var 0x5A4 0x0`

`setup_var 0x507 0x1`

Reboot from your primary drive. You Hack should boot normally. But don't forget to set up your BIOS settings.
Looks like we will need to do this every time after trigger «Reset to default settings» option in BIOS.
P.S. If you are interested in the details:

0x5A4 is CFG Lock option in BIOS
0x507 is System Time and Alarm Source option

This codes are not static and can be changed in future updates. You can [use this guide](https://translate.google.com/translate?sl=auto&tl=en&u=https%3A%2F%2Fjacyl4.github.io%2Fpost%2Fhackintosh-z370n-wifi-cfg-lock%2F) to find this code for future versions of BIOS.
