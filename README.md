AudioMoth - Flashing Basic Firmware Provided

STEP 1: Install the flashing application from this link :  https://www.openacousticdevices.info/flashing
STEP 2: Remove the extension (.dms) from the downloaded file so that it appears as just “flash”.

Reason for removal of .dms extension:
A file with a .dms extension is a file that has been downloaded and renamed by the Apple Safari web browser or the Apple Mail email client. It contains the contents of a file that did not have a file extension or was erroneously renamed when downloaded. The .dms extension is a result of a bug in Safari and Mail. (https://forums.macrumors.com/threads/safari-erroneously-adding-dms-extension-to-downloads.2080108/)
This is the reason why we remove the .dms file extension from the downloaded file.
Once the .dms extension is removed then the file becomes UNIX Executable file 

Functionality of the file FLASH
Flash is used to do following operations:

flash                                         ~ List the serial ports that are currently connected  
flash -i port                              ~ Show AudioMoth Serial Number 
flash -c port                             ~ Show current firmware CRC value
flash -u port file_location       ~ Uploads the new firmware (the file_location parameter contains the bin file location)
 
STEP 3: Open the terminal in the same directory and give permissions to the file flash by using the command : chmod a+x
STEP 4: Fork the project from GitHub from the following link: https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2
Also download the bin file that is available in this link.
STEP 5: Clone the project from the following link: https://github.com/OpenAcousticDevices/AudioMoth-Project
Make sure all the files are under one directory only.
STEP 6: Open the terminal in the same directory and run the command ./flash . This will list the ports that are connected. It will mostly return with the output as No Serial Port Found. 
STEP 7: Remove the batteries from the AudioMoth and turn the switch to CUSTOM on the AudioMoth. Connect the AudioMoth using a USB cable to the computer. Once its connected properly. The RED and GREEN LEDs will start blinking. Using a paperclip connect the PROG ends tightly till the LEDs stop blinking. This will enable the AudioMoth to enter the programming mode. Paperclip connection is shown below for the reference.

STEP 8: Once again run the command ./flash on the terminal.
You will be able to see a serial port with unique name appear. In case of Mac it will appear as: /dev/tty.usbmodemnumber
STEP 9: Now run the command:  ./flash -u portname .bin_file_location.
Example (./flash -u  /dev/ty.usbmodemnumber /Users/Admin/AudioMoth-Project/Audiomoth1.2.2.bin)
STEP 10: If everything goes well then after about 5-10 seconds the LEDs will start blinking again.

IN THE EVENT OF FAILURE TO DO FLASHING
Suppose the process fails and AudioMoth appears to be nonfunctional, it can be flashed again.
Make sure there are no batteries installed in the devices, hold the paperclip on the PROG tightly and then plug the USB Cable into the device. It is important that the paperclip is being held on the contacts when power is first applied to the device via the USB cable. The AudioMoth will then wake up and it will be in the programming mode once again. Then follow the steps 8-10 and the AudioMoth will be able to flash again.



AudioMoth - Flashing my own Firmware using my own .bin file

Pre-Requirements:
Since AudioMoth uses EFM32 Gecko Microcontroller to run which is made by Silicon Labs, they provided us with SIMPLICITY IDE which helps in flashing my own firmware without any overheads.

STEP 1: Install the flashing application from this link :  https://www.openacousticdevices.info/flashing
STEP 2: Remove the extension (.dms) from the downloaded file so that it appears as just “flash”.
STEP 3: Open the terminal in the same directory and give permissions to the file flash by using the command : chmod a+x
STEP 4: Fork the project from GitHub from the following link: https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2
Also download the bin file that is available in this link.
STEP 5: Clone the project from the following link: https://github.com/OpenAcousticDevices/AudioMoth-Project
Make sure all the files are under one directory only.
STEP 6: Download the Simplicity studio and do the following.

Using the Simplicity Studio IDE
To do so follow the quick steps:
	1.	Download the appropriate version of Simplicity Studio 4 for your operating system (https://www.silabs.com/products/development-tools/software/simplicity-studio) and follow the installation instructions.
	2.	Start the Simplicity Studio, log in the account you created in the step above, and select ‘Update Software’.
	3.	Select ‘Install by Product Group’ from the window that appears.
	4.	Select ’32-bit Micro-controllers to show a list of possible updates and download all the suggested entries in the ‘Recommended (based on selection in previous step) list.
	5.	Repeat the step above but now on next screen select GNU ARM Toolchain(v4.9.2015.q3) and 32 bit MCU SDK 5.2.2.0.
	6.	Once all the downloads have completed, go to Simplicity IDE and select IMPORT and then navigate to the ‘AudioMoth-Project’ folder that you have downloaded.
	7.	The project should appear and compile correctly.

STEP 7: Change the C code (src/main.c) as however as you like according to the needs. Then compile your code and build it.
STEP 8: Once the compilation is done it will make a new folder in the directory called ‘GNU ARM v4.9.3 - Release’. Inside that folder you can find the file called AudioMothProject.bin file. This bin file will be used to flash the new firmware.
STEP 9: Open the terminal in the same directory and run the command ./flash . This will list the ports that are connected. It will mostly return with the output as No Serial Port Found. 
STEP 10: Remove the batteries from the AudioMoth and turn the switch to CUSTOM on the AudioMoth. Connect the AudioMoth using a USB cable to the computer. Once its connected properly. The RED and GREEN LEDs will start blinking. Using a paperclip connect the PROG ends tightly till the LEDs stop blinking. This will enable the AudioMoth to enter the programming mode. Paperclip connection is shown below for the reference.

STEP 11: Once again run the command ./flash on the terminal.
You will be able to see a serial port with unique name appear. In case of Mac it will appear as: /dev/tty.usbmodemnumber
STEP 12: Now run the command:  ./flash -u portname .bin_file_location.
Example (./flash -u  /dev/ty.usbmodemnumber /Users/Admin/AudioMoth-Project/GNU\ ARM\ v4.9.3\ - \ Release/Audiomoth1.2.2.bin)
STEP 13: If everything goes well then after about 5-10 seconds the LEDs will start blinking again.

IF THE CODE DOESN’T WORK OR SOMETHING GOES WRONG: THINGS TO ASK?
Does the AudioMoth-Project build correctly before you make any changes? This code should make the AudioMoth respond to the Time App when in USB/OFF and just blink the LED when the switch is in DEFAULT or CUSTOM mode.
Are there any warnings in the console when you compile with the modified main.c file? They will appear as highlighted orange lines in the code. They can scroll past quickly and are sometimes hard to spot.
Can you confirm how big the resulting binary file is. Also, if you open the .hex file that appears in the same Release folder can you confirm that the first line starts with ':10400000'.
This link will solve some more issues that can be faced during flashing: https://www.openacousticdevices.info/support/configuration-support/help-with-basic-firmware-editing
