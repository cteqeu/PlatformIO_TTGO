# PlatformIO_TTGO


## Step 1
collect bootloader.bin, firmware.bin and partitions.bin files created with platformio  
## Step 2
locate esptool in the platformio packages directory  
	I used: C:\Users\XXXXXXXXX\.platformio\packages\framework-arduinoespressif32@3.10004.201016\tools\esptool.py  
## Step 3
Run command (sudo or admin may be needed)  

C:\Users\XXXXXXXXX\.platformio\packages\framework-arduinoespressif32@3.10004.201016\tools\esptool.py   
--chip esp32 --port COM4 -b 460800 --before default_reset --after hard_reset  write_flash --flash_mode dio   
--flash_size detect --flash_freq 40m 0x1000 bootloader.bin 0x8000 partitions.bin 0x10000 firmware.bin  
