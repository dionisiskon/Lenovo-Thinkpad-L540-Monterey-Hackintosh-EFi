# Lenovo-Thinkpad-L540-Monterey-Hackintosh-EFi

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

# Issues 
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
- VGA is a common problem among fans, even though using a VGA to HDMI fixes it, google it

# What to avoid
Never reset NVRAM in these laptops!!!! It may brick your laptop. It is a common issue among these specific models.

# Credits
  - breakfastdeep/Lenovo-Thinkpad-L540-MacOS-Monterey (When I first used Monterey, I utilized his EFI folder) 
  - receperoglu/HackintoshBigSurOpenCore_Thinkpad_L540 (When I was using Big Sur, I used this Big Sur repo so I simply added it in the credits)
