# ESP32_GameBoy
NintendoEntertainmentSystem Emulation on ESP32 and ILI9341 
#HW and Housing assembly
![image](https://github.com/ArturR0k3r/ESP32_GameBoy/assets/117598386/de34f7dd-283c-4dcc-a469-045ec0eb98d0)
![image](https://github.com/ArturR0k3r/ESP32_GameBoy/assets/117598386/0efdf5dd-534e-481a-a04c-eb7a57df8eda)


#Flashing the Software 
##1. Open ESPFlashDownloadTool_vXYZ.exe (Download Link: https://www.espressif.com/sites/default/files/tools/flash_download_tools_v3.6.4_0.rar)
		!!!If you work with mingw and esp idf and you get problems after using the ESPFlashTool (in my case, make doesn't work) go to!!!
		!!!the msys32 directory (<-"root" of msys/mingw) and run the autorebase.bat script...for me, after this everything works fine!!!
##2. Choose Button "ESP32 DownloadTool"
##3. Choose files to upload (Box with |...|) write adress to flash behind the @	
	first file 		bootloader.bin		0x1000
	second file		partitions.bin		0x8000
	3. file			nesemu.bin			0x10000
	4. file			roms.txt			0x68000		!you've to change the file according your needs - otherwise you can only choose 3 roms!
	5. file			yourRom.nes			0x69000		!make sure the roms are not greater than the partition-size.		
	6. file			yourNextRom.nes		0x.....
	7. file			yourNextRom2.nes	0x.....
		.
		.
		.
		
		Flash the Roms to this Adresses
	No.		  Adress 		Size(up to...KB)	
	rom01 	  0x69000			100
	rom02	  0x82000			260
	rom03	  0xc3000			388
	rom04	 0x124000			132
	rom05    0x145000			260
	rom06	 0x186000			100
	rom07	 0x19f000			100
	rom08	 0x1b8000			100
	rom09	 0x1d1000			772
	rom10	 0x292000			516
	rom11	 0x313000			296
	rom12	 0x35d000			260
	rom13	 0x39e000			260
	rom14	 0x3df000			132	

##4.	Choose the following Settings

		SPI SPEED: 40MHz

		SPI MODE: DIO

		FLASH SIZE: 32Mbit(=4MB)

		COM: can be found in Device Manager
		
##5.	Press "Start", when finished "Stop"
	After a Reset/Restart(dis-reconnect the USB) the Emulator works
