# TTGO-LoRa-APRS-WIFI-config
How to setup several wifi access points on DL9SAU LoRa APRS firmware (TTGO-Lora32 hard)

Here I will try to explain how to setup several wifi access points on the DL9SAU firmware for LoRa APRS with TTGO Lora 32 circuits

1. First you must download the project at https://github.com/dl9sau/TTGO-T-Beam-LoRa-APRS
2. Unzip it into some folder and remember it
( If you have already installed the Visual Studio Code jump to 5 )
3. Install VS Code software at your PC
4. Install PlatformIO add-on
5. Open the folder where you have unzipped the DL9SAU project
6. Wait until all dependencies are solved.
7. Check that you have selected the right circuit and version environment
8. With the circuit connected to the computer, select the proper serial port (in my case, COM8
9. open the file "platformio.ini" and add the following line on the [env] section:
    upload_port = COMn (where n is the number of the port assigned to the circuit plate )
10. save this file
11. Now, on the left menu, open the folder "data". There you should find 2 files: "preferences.cfg" and "wifi.cfg". If you have already configured and installed this firmware, you know where they are.
12. In this case, we want only to modify the "wifi.cfg" file, to add / set our preferred wifi access points.
13. Open the file. By default it shows 2 wifi access points unde the section AP. Leave the "SelfAP_PW" as is.
14. Type your "SSID"s and "password" values. If you have more than 2 wifi nets, add them after the 2nd.
    Be aware that the different definitions must be separated by commas, except the last one.
15. If you want a priority wifi network to be used, mark it as "prio": 1 (see the default values )
16. Now, once all configured, follow these steps:
17. Select the ant symbol (PlatformIO) on the left menu
18. Deploy the Platform folder. If you cannot find it, be sure that you have selected the proper Project Environment and the circuit is connected to the computer
If you have the firmware installed jump the following step
19. Select the option "Erase Flash" and wait until finished
20. Choose now "Build Filesystem Image" and wait until step is completed
21. Next, choose "Upload Filesystem Image", wait and check that your igate circuit is reset and rebooted
22. Last, use the options "Build" and "Upload" in the General folder.
That's all. Next time you boot the igate, it will try to find the several wifi networks defined. If no one is found, it will turn to AP mode

    
