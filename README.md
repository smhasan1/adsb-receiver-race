# ADSB-Receiver-RACE

This is a detailed comprehensive tutorial on how to setup Runtime for Airspace Concept Evaluation ([RACE](http://nasarace.github.io/race/)) software for Live Data Import from a remote ADS-B receiver. This tutorial also includes a detailed instruction on how to set up the ADS-B receiver server using a raspberry pi.  

**Race Software Screenshots:**  


<img src="https://user-images.githubusercontent.com/19510655/39539052-af02f80c-4e0c-11e8-80a3-5cb6f481da84.png" width="600">
<br />

**List of Items:**  

<img src="https://user-images.githubusercontent.com/19510655/39546062-1cb914b2-4e21-11e8-8d59-09994cb5b10e.jpg" width="600">  

1. Raspberry Pi 3 with an SD card  
* https://www.amazon.ca/Raspberry-Pi-RASPBERRYPI3-MODB-1GB-Model-Motherboard/dp/B01CD5VC92 &  
* https://www.amazon.ca/Kingston-microSDHC-Class-Memory-SDC4/dp/B00200K1TS/ref=sr_1_3?ie=UTF8&qid=1525292339&sr=8-3&keywords=kingston+micro+sd+card+8gb    
2. FlightAware Pro Stick USB ADS-B Receiver
* https://www.amazon.ca/gp/product/B01D1ZAP3C/ref=oh_aui_detailpage_o08_s00?ie=UTF8&psc=1  

3. Micro USB to USB  
* https://www.amazon.ca/Anker-PowerLine-Micro-USB-10ft/dp/B012WF7ORW/ref=sr_1_4?s=electronics&ie=UTF8&qid=1525292941&sr=1-4&keywords=micro+usb+charge+cable  

4. SMA Male to N-Type Male Cable  
* https://www.amazon.ca/gp/product/B007PPHVFK/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1  
Or  
https://www.digikey.com/products/en?keywords=277-3058-ND  

5. Ethernet Cable
* https://www.amazon.ca/Fosmon-Network-Ethernet-Router-Printer/dp/B0057I2IS2/ref=sr_1_8?ie=UTF8&qid=1525293355&sr=8-8&keywords=ethernet%2Bcable&th=1  

6. 1090MHz ADS-B Antenna  
* https://www.amazon.ca/gp/product/B00WZL6WPO/ref=oh_aui_detailpage_o04_s00?ie=UTF8&psc=1  

**Final Setup:**  

<img src="https://user-images.githubusercontent.com/19510655/39548164-b3762a1a-4e27-11e8-8d2b-6a7b102c70a9.jpg" width="600">

**Background:**  

Airplanes use ADS–B surveillance technology to determine its location via satellite navigation and periodically broadcasts it, so it can be tracked. It transmits raw data at 1090 MHz and we use a 1090 MHz antenna to receive it. The antenna then sends those raw values to the user, using a USB ADS-B Receiver, and the user decodes the raw data using dump1090 software. Finally, the RACE software is used to overlay the flight locations on a map and it's updated regularly to show flight movement. This whole process is described briefly in this research poster:  

<img src="https://user-images.githubusercontent.com/19510655/39786650-7b927d66-52ef-11e8-98c0-ed9f2845b730.jpg" width="1000">  

There are several ways of setting up this project. In our case we've used a Raspberry Pi 3 (portability advantage) to send signals to multiple users over a server (the server is hosted within the raspberry pi). This step may very well be skipped and the USB ADS-B receiver can be directly connected to the user's computer. Additionally RACE isn't the only software that can overlay flight data on a map, for example FlightRadar24 does the same thing (https://www.flightradar24.com/). However RACE has a unique framework built on Scala and Akka, that deals with parallelism quite affectively. For example if you'd like to have airplane data layer and weather data layer plus other layers, all on top of each other. In that case RACE would fair better than most other layered framework approaches.  

* To install Race on your computer:  
http://nasarace.github.io/race/usage/running.html  

* To setup a server on Raspberry Pi 3 and install dump1090 software:  
http://www.satsignal.eu/raspberry-pi/dump1090.html  
&
https://github.com/jprochazka/adsb-receiver  

The links I've mentioned has a step by step tutorial, but it's not always the case the each step will work perfectly. It's best practice to understand the task and the google for the required steps to achieve it. At times going though several google links would result in success.  

Please let me know if anyone has any questions regarding the installation or anything else.  
Email: hasan_msyed@hotmail.com  


# License

    Copyright (c) 2016, United States Government, as represented by the
    Administrator of the National Aeronautics and Space Administration.
    All rights reserved.

    The RACE - Runtime for Airspace Concept Evaluation platform is licensed
    under the Apache License, Version 2.0 (the "License"); you may not use
    this file except in compliance with the License. You may obtain a copy
    of the License at http://www.apache.org/licenses/LICENSE-2.0.

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
