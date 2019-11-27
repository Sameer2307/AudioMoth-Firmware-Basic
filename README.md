{\rtf1\ansi\ansicpg1252\cocoartf1561\cocoasubrtf600
{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;\red53\green53\blue53;\red0\green0\blue255;\red0\green0\blue0;
\red251\green2\blue7;\red255\green255\blue255;\red51\green51\blue51;\red20\green157\blue82;\red27\green113\blue222;
\red220\green161\blue13;\red0\green0\blue255;\red8\green23\blue24;}
{\*\expandedcolortbl;;\cssrgb\c27059\c27059\c27059;\cssrgb\c1680\c19835\c100000;\cssrgb\c0\c0\c0;
\cssrgb\c100000\c14913\c0;\cssrgb\c100000\c100000\c100000;\cssrgb\c25882\c25882\c25882;\cssrgb\c0\c66667\c39608;\cssrgb\c11765\c53333\c89804;
\cssrgb\c89412\c68627\c3922;\cssrgb\c1680\c19835\c100000;\cssrgb\c2353\c11765\c12549;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc0\levelnfcn0\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{decimal\}.}{\leveltext\leveltemplateid1\'02\'00.;}{\levelnumbers\'01;}\fi-360\li720\lin720 }{\listname ;}\listid1}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}}
\paperw11900\paperh16840\margl1440\margr1440\vieww16020\viewh11520\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\b\fs36 \cf0 \ul \ulc0 AudioMoth - Flashing Basic Firmware Provided\

\b0\fs24 \ulnone \

\b STEP 1
\b0 : Install the flashing application from this link : 
\f1 \cf2  {\field{\*\fldinst{HYPERLINK "https://www.openacousticdevices.info/flashing"}}{\fldrslt \cf3 https://www.openacousticdevices.info/flashing}}\cf3 \

\b \cf4 STEP 2: 
\b0 Remove the extension (.dms) from the downloaded file so that it appears as just \'93flash\'94.\
\
\cf5 \ul \ulc5 Reason for removal of .dms extension:\cf4 \ulc4 \
\pard\pardeftab720\partightenfactor0
\cf4 \cb6 \expnd0\expndtw0\kerning0
\ulnone \outl0\strokewidth0 \strokec7 A file with a 
\b \cb1 \strokec8 .dms
\b0 \cb6 \strokec7  extension is a file that has been downloaded and renamed by the Apple Safari web browser or the Apple Mail email \cb1 \strokec9 client\cb6 \strokec7 . It contains the contents of a file that did not have a file extension or was erroneously renamed when downloaded. The .dms extension is a result of a \cb1 \strokec9 bug\cb6 \strokec7  in Safari and Mail. (\cf3 \ul \ulc3 \strokec10 https://forums.macrumors.com/threads/safari-erroneously-adding-dms-extension-to-downloads.2080108/\cf4 \ulnone \strokec7 )\cf4 \cb1 \strokec4 \
This is the reason why we remove the .dms file extension from the downloaded file.\
Once the .dms extension is removed then the file becomes UNIX Executable file
\fs29\fsmilli14667  
\fs24 \
\cf5 \ul \ulc5 \
Functionality of the file FLASH\
\cf4 \ulnone Flash is used to do following operations:\
\

\b flash                                         ~ 
\b0 List the serial ports that are currently connected
\b   \
flash -i port                              ~ 
\b0 Show AudioMoth Serial Number 
\b \
flash -c port                             ~ 
\b0 Show current firmware CRC value
\b \
flash -u port file_location       ~ 
\b0 Uploads the new firmware (the file_location parameter contains the bin file location)\
 \

\b STEP 3: 
\b0 Open the terminal in the same directory and give permissions to the file flash by using the command : 
\b chmod a+x\
STEP 4: 
\b0 Fork the project from GitHub from the following link: {\field{\*\fldinst{HYPERLINK "https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2"}}{\fldrslt https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2}}\
Also download the bin file that is available in this link.\

\b STEP 5: 
\b0 Clone the project from the following link: {\field{\*\fldinst{HYPERLINK "https://github.com/OpenAcousticDevices/AudioMoth-Project"}}{\fldrslt https://github.com/OpenAcousticDevices/AudioMoth-Project}}\
Make sure all the files are under one directory only.\

\b STEP 6: 
\b0 Open the terminal in the same directory and run the command 
\b ./flash
\b0  . This will list the ports that are connected. It will mostly return with the output as 
\b No Serial Port Found
\b0 . \

\b STEP 7: 
\b0 Remove the batteries from the AudioMoth and turn the switch to 
\b CUSTOM
\b0  on the AudioMoth. Connect the AudioMoth using a USB cable to the computer. Once its connected properly. The RED and GREEN LEDs will start blinking. Using a paperclip connect the PROG ends tightly till the LEDs stop blinking. This will enable the AudioMoth to enter the programming mode. Paperclip connection is shown below for the reference.\
\pard\pardeftab560\slleading20\pardirnatural\qc\partightenfactor0
\cf2 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 {{\NeXTGraphic b31671_88528e42407f4ad0a769a879d54538e5~mv2.png \width4680 \height4500 \appleattachmentpadding0 \appleembedtype0 \appleaqc
}¬}\
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0

\b \cf4 STEP 8: 
\b0 Once again run the command 
\b ./flash
\b0  on the terminal.\
You will be able to see a serial port with unique name appear. In case of Mac it will appear as: 
\b /dev/tty.usbmodemnumber
\b0 \

\b STEP 9: 
\b0 Now run the command: 
\b  ./flash -u portname .bin_file_location.\

\b0 Example (./flash -u  /dev/ty.usbmodemnumber /Users/Admin/AudioMoth-Project/Audiomoth1.2.2.bin)\

\b STEP 10: 
\b0 If everything goes well then after about 5-10 seconds the LEDs will start blinking again.\
\ul \

\b IN THE EVENT OF FAILURE TO DO FLASHING\

\b0 \ulnone Suppose the process fails and AudioMoth appears to be nonfunctional, 
\b it can be flashed again.\

\b0 Make sure there are no batteries installed in the devices, hold the paperclip on the PROG tightly and then plug the USB Cable into the device. It is important that the paperclip is being held on the contacts when power is first applied to the device via the USB cable. The AudioMoth will then wake up and it will be in the programming mode once again. Then follow the steps 8-10 and the AudioMoth will be able to flash again.\
\cf2 \
\
\ul \

\b\fs36 \cf4 \ulc4 AudioMoth - Flashing my own Firmware using my own .bin file\

\b0\fs24 \cf2 \ulnone \
\cf4 Pre-Requirements:\
Since AudioMoth uses EFM32 Gecko Microcontroller to run which is made by Silicon Labs, they provided us with SIMPLICITY IDE which helps in flashing my own firmware without any overheads.\
\cf2 \

\f0\b \cf0 STEP 1
\b0 : Install the flashing application from this link : 
\f1 \cf2  {\field{\*\fldinst{HYPERLINK "https://www.openacousticdevices.info/flashing"}}{\fldrslt \cf11 https://www.openacousticdevices.info/flashing}}\cf11 \
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\b \cf4 STEP 2: 
\b0 Remove the extension (.dms) from the downloaded file so that it appears as just \'93flash\'94.\
\pard\pardeftab720\partightenfactor0

\b \cf4 \expnd0\expndtw0\kerning0
STEP 3: 
\b0 Open the terminal in the same directory and give permissions to the file flash by using the command : 
\b chmod a+x\
STEP 4: 
\b0 Fork the project from GitHub from the following link: {\field{\*\fldinst{HYPERLINK "https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2"}}{\fldrslt https://github.com/OpenAcousticDevices/AudioMoth-Firmware-Basic/releases/tag/1.2.2}}\
Also download the bin file that is available in this link.\

\b STEP 5: 
\b0 Clone the project from the following link: {\field{\*\fldinst{HYPERLINK "https://github.com/OpenAcousticDevices/AudioMoth-Project"}}{\fldrslt https://github.com/OpenAcousticDevices/AudioMoth-Project}}\
Make sure all the files are under one directory only.\

\b STEP 6: 
\b0 Download the Simplicity studio and do the following.\

\b \cf2 \kerning1\expnd0\expndtw0 \
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0

\b0 \cf5 Using the Simplicity Studio IDE
\b \cf2 \

\b0 \cf4 To do so follow the quick steps:\
\pard\tx220\tx720\pardeftab560\li720\fi-720\slleading20\pardirnatural\partightenfactor0
\ls1\ilvl0\cf4 {\listtext	1.	}Download the appropriate version of Simplicity Studio 4 for your operating system ({\field{\*\fldinst{HYPERLINK "https://www.silabs.com/products/development-tools/software/simplicity-studio"}}{\fldrslt \expnd0\expndtw0\kerning0
https://www.silabs.com/products/development-tools/software/simplicity-studio}}\expnd0\expndtw0\kerning0
) and follow the installation instructions.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	2.	}Start the Simplicity Studio, log in the account you created in the step above, and select \'91Update Software\'92.\
{\listtext	3.	}Select \'91Install by Product Group\'92 from the window that appears.\
{\listtext	4.	}Select \'9232-bit Micro-controllers to show a list of possible updates and download all the suggested entries in the \'91Recommended (based on selection in previous step) list.\
{\listtext	5.	}Repeat the step above but now on next screen select 
\b GNU ARM Toolchain(v4.9.2015.q3) 
\b0 and 
\b 32 bit MCU SDK 5.2.2.0.
\b0 \
{\listtext	6.	}Once all the downloads have completed, go to Simplicity IDE and select IMPORT and then navigate to the \'91AudioMoth-Project\'92 folder that you have downloaded.\
{\listtext	7.	}The project should appear and compile correctly.\
\pard\tx566\pardeftab560\slleading20\pardirnatural\partightenfactor0
\cf4 \expnd0\expndtw0\kerning0
\

\b STEP 7: 
\b0 Change the C code (src/main.c) as however as you like according to the needs. Then compile your code and build it.\

\b STEP 8: 
\b0 Once the compilation is done it will make a new folder in the directory called \'91GNU ARM v4.9.3 - Release\'92. Inside that folder you can find the file called AudioMothProject.bin file. This bin file will be used to flash the new firmware.\
\pard\pardeftab720\partightenfactor0

\b \cf4 STEP 9: 
\b0 Open the terminal in the same directory and run the command 
\b ./flash
\b0  . This will list the ports that are connected. It will mostly return with the output as 
\b No Serial Port Found
\b0 . \

\b STEP 10: 
\b0 Remove the batteries from the AudioMoth and turn the switch to 
\b CUSTOM
\b0  on the AudioMoth. Connect the AudioMoth using a USB cable to the computer. Once its connected properly. The RED and GREEN LEDs will start blinking. Using a paperclip connect the PROG ends tightly till the LEDs stop blinking. This will enable the AudioMoth to enter the programming mode. Paperclip connection is shown below for the reference.\
\pard\pardeftab560\slleading20\pardirnatural\qc\partightenfactor0
\cf2 \kerning1\expnd0\expndtw0 {{\NeXTGraphic b31671_88528e42407f4ad0a769a879d54538e5~mv2.png \width4680 \height4500 \appleattachmentpadding0 \appleembedtype0 \appleaqc
}¬}\pard\pardeftab560\slleading20\pardirnatural\qc\partightenfactor0
\cf2 \
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0

\b \cf4 STEP 11: 
\b0 Once again run the command 
\b ./flash
\b0  on the terminal.\
You will be able to see a serial port with unique name appear. In case of Mac it will appear as: 
\b /dev/tty.usbmodemnumber
\b0 \

\b STEP 12: 
\b0 Now run the command: 
\b  ./flash -u portname .bin_file_location.\

\b0 Example (./flash -u  /dev/ty.usbmodemnumber /Users/Admin/AudioMoth-Project/GNU\\ ARM\\ v4.9.3\\ - \\ Release/Audiomoth1.2.2.bin)\

\b STEP 13: 
\b0 If everything goes well then after about 5-10 seconds the LEDs will start blinking again.\cf4 \expnd0\expndtw0\kerning0
\
\pard\tx566\pardeftab560\slleading20\pardirnatural\partightenfactor0
\cf4 \

\b \ul IF THE CODE DOESN\'92T WORK OR SOMETHING GOES WRONG: THINGS TO ASK?\
\pard\pardeftab720\partightenfactor0

\b0 \cf4 \cb6 \ulnone \outl0\strokewidth0 \strokec12 Does the AudioMoth-Project build correctly before you make any changes? This code should make the AudioMoth respond to the Time App when in USB/OFF and just blink the LED when the switch is in DEFAULT or CUSTOM mode.\cf4 \cb1 \strokec4 \
\cf4 \cb6 \strokec12 Are there any warnings in the console when you compile with the modified main.c file? They will appear as highlighted orange lines in the code. They can scroll past quickly and are sometimes hard to spot.\cf4 \cb1 \strokec4 \
\cf4 \cb6 \strokec12 Can you confirm how big the resulting binary file is. Also, if you open the .hex file that appears in the same Release folder can you confirm that the first line starts with ':10400000'.\cf4 \cb1 \strokec4 \
\cf4 \cb6 \strokec12 This link will solve some more issues that can be faced during flashing: \cf3 \strokec10 https://www.openacousticdevices.info/support/configuration-support/help-with-basic-firmware-editing\cb1 \strokec4 \
}