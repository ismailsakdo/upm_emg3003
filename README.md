# UPM Bachelor Environmental Management: EMG3003 Environmental Monitoring System
## Chapter 1: Introduction
This module is created to assist the students regarding the use of IoT technology in managing the environmental data and thus help the decision making process. In the begining, we need to understand the following ideas, related to Big Data Analytics (BDA), IoT and their applications and insight.

### Big Data
The big data is the new paradigm where the use of data is importance in making decision. The journey of data is everything with regard to the intelligent development. The basic idea will be DATA > INFORMATION > KNOWLEDGE > INSIGHT > VALUE

### IoT
The concept of IOT can be utilized by the use of MCU, SBC and Computer. Its begin with the capability of the computer in managing numbers of operations. Then the evolution of SBC (Raspberry Pi), lead to the development of the advancement of MCU/ PLC and else.

### Dashboard
### Intelligent Environmental Monitoring

## Chapter 2: Fundamental
### MCU

### Sensor

### Software
#### Software Step 1: IDE Setup
1) Navigate arduino website: https://arduino.cc/software
2) Download the software according to your Operating System (OS)
3) Install the Arduino Software including the related USB Driver
4) Copy the following link: https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
5) Go to File > Preferences > URL/ Board Manager, paste the above link followed by ","
6) Click OK
7) Then go to Tool Menu > Board > Board Managers
8) In the board manager, type: ESP32
9) Click install on the ESP32 by Espressif
10) Done Installation

#### Software Step 2:
Installation of Libraries
*There are two ways to install the libraries, first using the Arduino Library Manager, second using the folder/ zip file.

##### Method 1 (Install from Library Manager)
1) Go to Sketch Menu > Include Library > Manage Libraries
2) Install the library as you need. 

##### Method 2 (Install from zip file)
1) Navigate the source
2) Download the Zip file
3) Extract the Zip file
4) Rename the folder, remove the "-master" extension if any
5) Copy the unzip folder into Arduino library folder
6) Paste the folder into Arduino > libraries

##### Method 2.1 (Install from the Github/ Repo)
1) Navigate to the link
2) Download
3) Extract
4) Rename the folder, remove the "-master" name/ extension (if any)
5) Copy the unzip and rename folder
6) Paste into the Arduino > libraries folder

##### List of Libraries:
1) rtclib
2) rtc by makuna
3) MQunifiedsensor
4) Adafruit_GFX
5) Adafruit_SSD1306
6) Adafruit_PM25AQI
7) ThingSpeak
8) WiFiManager
9) SD card if not present link: https://github.com/espressif/arduino-esp32

#### Software Step 3:
1) Identify the urban environmental health analytics issues to be explore
2) Perform secondary data analysis (screening)
3) Priotitize the location of interest and start prototyping
4) Refer following connection [<img src="https://github.com/ismailsakdo/uitm_emsa/blob/main/Connection_bb.png" width="500px">]
5) Test each of the sensor using one module at one time
6) Follow Chapter 4

#### Arduino IDE
1) Install the ESP32 Board Manager (refer to Chapter 1 & 2)
2) Upload Sketch of RTC by Makuna
3) Upload sketch of Step 1: 

### Cloud Technology
This chapter, you can begin to register the following account:
1) IoT Thingspeak Cloud
2) IFTTT for the notification
3) 

## Chapter 3: Creating the Unit
In general, there are numbers of ways to connect the sensor and the MCU. This step, please follow the ideas below:
1) 3 Wire - GND, VCC, SIG
2) 4 Wire (I2C) - GND, VCC, SDA, SCL
3) 6 Wire (SPI) - GND, VCC, CS, MOSI, MISO, SCK
4) Transmit and Received - GND, VCC, Rx/ Tx

## Chapter 4: Programming
This chapter, you should familiarize with the basic C++ programming and relevant sketch to connect the sensor and MCU.

#### Programing Step 1: Familiarize The MCU + Sensor
##### Irsensor
1) Connect IR sensor Pin (4)
2) Upload code: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/irsensor.ino

##### Irsensor + OLED Display
1) Connect IR Sensor Pin(4)
2) Connect the OLED display (SDA, SCL) - I2C
3) Upload code: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/irsensor_oled.ino

##### Irsensor + Oled + Additional Sensor (MQ135)
1) Connect IR sensor (4)
2) Conenct Oled
3) Connect MQ135
4) Upload Code: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/irsensor_oled_mq135.ino

##### IRsensor + oled + MQ + i2c sensor (BMP280)
1) Follow step 1-3 as mention in previous
2) Install additional sensor
3) Upload code (BMP280): https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/ir_oled_mq_tp.ino
4) Upload Code (SHT21): https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/ir_oled_mq_th.ino

###### Let's Make Datalogger
1) Setup the RTC (Using RTC by MAKUNA)
2) Setup the SD Card (Ensure format the SD Card - FAT32) - name file as data.txt
3) Upload the CODE: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/ir_oled_mq_tp_datalogger.ino
4) Observe the result in SD Card Reader

##### Let's Make Even Challenging (IOT)
1) Follow steps until particle sensor
2) Register Thingspeak account > create channel > copy ID + API Write Key
3) Ensure to try 2 times, upload with and without comment this LINE: //wifiManager.resetSettings(); 
4) Upload Code: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/ir_oled_mq_tp_datalogger_pms_iot.ino
5) Upload Code 2 (Cleaner SD Card Output): https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/final_all.ino
6) Connect to internet (Wataverse Technology)
7) Go to link: http://192.168.4.1/
8) Insert your username + password

##### Final Moment/ Express way
1) Upload RTC by Makuna
2) Edit your Thingspeak ID and API WRITE KEY
3) Upload the Code1 (8 parameters) OR: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/final_all.ino
4) Upload the Code2 (10 parameters - PMS all): https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/final_fullPMS.ino

##### Latest Code (30/4/2023)
1) Upload RTC by Makuna
2) Edit your Thingspeak ID, API Write Key, Username + Password (WiFi)
3) Upload the Code Final (WiFi HardCode): https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/airqualityFinal.ino

##### TroubleShoot Problem
1) Error on the COM Port - Download driver from the following Link: https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads
2) Error on the ESP32 Compiling - Uninstall the Arduino IDE, Install Back the IDE, Install the Library
3) Error on the ESP32 Compiling - Update the Arduino IDE board Manager

##### Checking the Output
1) Check your Thingspeak Channel
2) Check your SD Card
3) Check the SD Card data into the following column: Date | Time | Temperature | Pressure | co2 | pm03 | pm01 | pm05 | pm50 | pm25 | pm10 | ir detect

## Chapter 5: Cloud IoT
### IoT Cloud Services
### Seting Up the Fetch

## Chapter 6: Dashboard & Visualization
### Database for Urban Analytics (Air Quality Datalogger)
The datalogger is now ready for data collection and you should ensure that the power supply is sufficiently provide for the unit together with the stable internet connection. Now is the part where we will import the thingspeak data from the IOT Analytics into the Google Sheet for further action/ dashboard.

### Dashboard Thingspeak + Google Site
Now we will construct normal Google Site for our display of the Thingspeak Chart into the Google Site.

### Personalized Dashboard Using Google Appsheet + Google Sheet + Goolge App Script
Now this time we will using the Google Sheet as databases retrive from the IOT Thingspeak server.
1) Setup the Google Sheet (Insert Relevant Headers)
2) Setup the Google App Script
3) Copy coding from the following link: https://raw.githubusercontent.com/ismailsakdo/uitm_emsa/main/GOODimportThingspeakFinal.gs
4) Activate, save and run accordingly

## Chapter 7: Intelligent
