# Lenovo-Thinkpad-L540-Monterey-Hackintosh-EFi
I do not take any responsibility, in case you bricked your laptop! I suggest always trying out the EFI folder using a USB drive and install it afterwards.
Before making any new changes, you can backup the original config.plist file in the same folder as the new one, just in case something goes wrong and you need to restore it.

If something goes wrong with the config.plist, your laptop may not boot up. If you don't have a Mac OS USB with an EFI folder, so that the laptop can boot up, 
use the OpenShell that is included in the Opencore boot-up menu. I used it to remove a faulty kext from config.plist or you can use it to restore the aforementioned backed up config.plist. Example:

1. type "fs0:" and press enter in the shell to check out the contents. (Try it until you find the drive with the EFI folder)
2. "cd EFI" and press enter to go inside the EFI folder, and then "cd OC" and press enter to go inside the OC folder where the config.plist file is located
3. "edit config.plist" and press enter to edit the file and change faulty addition of config.plist.
4. Ctrl + S press on keyboard to save and then you can reboot pc 

# Specs of original L540

  - CPU: Intel 4300M
  - GPU: Intel HD 4600 (Integrated)
  - STORAGE: 128GB SSD
  - RAM: 8GB RAM
  - AUDIO: ALC292
  - SD CARD READER: Realtek RTS5227 SD CARD READER

# How to use

Generate SMBIOS and include them in PlatformInfo -> Generic -> SystemUUID, SystemSerialNumber, SystemMLB.
For the ROM, google it. You can use your network card's MAC Address.

# Issues that were encountered and solved

- USB Ports 
- Camera  
- Keyboard Shortcuts were a bit messed up
- Headphone jack wasn't working 
- Blueetooth hash mismatch problem
- SD Card Reader

# What Works

- USB Ports (Created kext with Hackintool for my specific Notebook)
- Camera (Same as USB Ports)
- Audio (Fixed using alcid = 59 in boot-args)
- SD Card Reader (RealtekCardReader + RealtekCardReaderFriend didn't work, but Sinetek-rstx did)
- Bluetooth hash mismatch (UEFI -> ProtocolOverrides -> HashServices -> True)
- Wifi (Either itlwm + heliport or Airportitwlm works. I use Airportitlwm because I find it better)

# What doesn't work

- Possibly Smartcard Reader, even though I haven't tested it and is recognized by the system
- VGA is a common problem encountered in hackintosh machines, even though using a VGA to HDMI fixes it. Google it!

# Bugs

- Some Thinkpad keyboard shortcuts may not work. I have a faulty keyboard and can't test it.
- Sinetek rstx may interefere with the sleep of laptop, even though there is a thread in the repo of sinetek-rstx that says how to resolve this issue.
- SD Card Reader has an unsigned class so every time you boot it will say unknown card drive, but I promise it works! I simply drag it using COMMAND + mouse click to the middle of the screen and it dissapears from the status bar

# What to avoid
Never reset NVRAM in these laptops!!!! It may brick your laptop. It is a common issue among these specific models.

# Credits
  - breakfastdeep/Lenovo-Thinkpad-L540-MacOS-Monterey (When I first used Monterey, I utilized his EFI folder) 
  - receperoglu/HackintoshBigSurOpenCore_Thinkpad_L540 (When I was using Big Sur, I used this Big Sur repo so I simply added it in the credits)
  - cholonam/Sinetek-rtsx (A repo for the SD card reader kext)
