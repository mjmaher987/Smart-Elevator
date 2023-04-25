# Smart Elevator Manager
## About
Smart Elevator Manager is a project of embedded system design that implements a smart elevator system using Raspberry Pi and Arduino for face recognition and fingerprint authorization with real-time monitoring through a mobile device, utilizing modules such as a fingerprint sensor, keypad, buzzer, distance sensor, and a web progressive app.

## Contributors
* Mohammad Sadegh Salimi

* Parsa Sharifi

* Alireza Foroodnia

* Mohammad Javad Maheronnaghsh

<img src="https://user-images.githubusercontent.com/45296858/217477922-8b27599c-1a28-4232-8c24-69ef5d07f824.jpg" width=50% height=50%>

## Help Links
* https://wokwi.com : simulating raspberry pi and arduino online
* https://github.com/raspberrypi/pico-micropython-examples : source code of raspberry pi samples
* https://electropeak.com/learn/interfacing-r308-biometric-fingerprint-sensor-module-with-arduino/ : Fingerprint Sensor

## Project Description
This is a description of a smart elevator system. The elevator only moves for individuals with registered fingerprint or face recognition. Face recognition is available outside the elevator and on every floor. For testing and simplification, two or three floors can be used.

Each floor can be modeled using a mobile device to receive images. The elevator has two modes: automatic mode, in which it moves only when it recognizes registered faces or fingerprints, and guest mode, in which it moves even if the face and fingerprints are not registered.

The elevator can either move up or down. For example, if the elevator is on floor 7 and moving down and a person is waiting on floor 3, the elevator will move down to floor 3. If the person on floor 3 wants to move up, and no one wants to go down or walk down, the direction of the elevator will change. Note that while the elevator is moving to the desired floor, it can be seen in real-time on the mobile device on the desired floor.

## Structure
### Simple Apps - Raspberri Pi
In this project, I have made a folder named 'Simple Apps - Raspberri Pi' that concludes the neccessary simple python codes to complete this project. I think it is also a good tutorial for new raspberry pi users.
### Simple Apps - Arduino
In this project, I have made a folder named 'Simple Apps - Arduino' that concludes the neccessary simple python codes to complete this project. I think it is also a good tutorial for new arduino users.

### Controller.ino
This file consists of the main codes to run this project.
It is a mixture of main.ino file (that is the state-controller), and all_modules.ino file (that is the abstraction of needed_methods for modules).
After completing this file, our code is finished (except web app).
### Merged - Primary - V1.ino
This file is the last version of file that is a mixture of controlling file and source codes for Arduino.
This file is uploaded on Arduino and then it works.
## Modules
#### Fingerprint Sensor
This module is used to authorize the people. It checks the fingerprint of people, if it knows the fingerprint, send us an acknowledge that is the id of that user.
If the fingerprint was not saved before, it sends an acknowledge telling us that the fingerprint was not recognized.

<img src="https://user-images.githubusercontent.com/45296858/217478372-8adc5ea0-1d8f-4928-a03e-d4bc0f9e1ac1.png" width=30% height=30%>

Source of image: https://www.adafruit.com/product/751

#### Keypad
It is 4*4 keypad. We can give it a hashtable that maps each of these 16 keys to 16 characters. we can define this hashtable by ourselves.

<img src="https://user-images.githubusercontent.com/45296858/217478588-8498bac6-fb8d-4a8e-a02d-d0b4d387f405.png" width=40% height=40%>

Source of image: https://lastminuteengineers.com/arduino-keypad-tutorial/

#### Light Sensor
This is a module for detecting light intensity, but unfortunately it broke down in our project due to connecting GND and VDD in reversly.

<img src="https://user-images.githubusercontent.com/45296858/217478976-71c68fd4-8bdd-4cb2-ac1d-1fcb6a42fabd.png" width=30% height=30%>

Source of image: https://www.walmart.ca/en/ip/Light-Intensity-Detection-Sensor-Photoresistor-Module-4-Pin-for-Arduino-UNO/PRD0ZRILHDNCH9E

#### Buzzer
It is a very simple module to create sound. We can define the frequency of sound in our code.

<img src="https://user-images.githubusercontent.com/45296858/217479132-093f2ea9-34f3-4c50-ab2e-949b1146effa.png" width=30% height=30%>

Source of image: https://www.ebay.co.uk/itm/253395042040

#### Arduino Board
This is a microcontroller that has two main functions named "setup" and "loop".
Working with arduino is very easy. It runs setup function once and loop function infinitely.
We can add arbitrary functions due to our needs. We run it by Arduino IDE.

<img src="https://user-images.githubusercontent.com/45296858/217478051-d2655123-8b18-464d-a9cc-105235340ade.png" width=30% height=30%>

Source of image: https://www.flickr.com/photos/sparkfun/8406865680/

#### Distance Sensor
It it used to tell use the distance of nearest thing to this sensor.
It works in a way that sends a ultra-sound using one of its circular parts and waits until receives that sent wave.
Then calculates the time between sending and receiving. Then we can calculate the distance using the wave speed.

<img src="https://user-images.githubusercontent.com/45296858/217479401-20f543a8-d151-4644-b4ec-f8fb301d742c.png" width=40% height=40%>

Source of image: https://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/

#### Relle and Remote

## Web Progressive App
You can find simple version of web page here:
* https://smsadegh19.github.io/SmartElevatorApp/

<img src="https://user-images.githubusercontent.com/45296858/217479479-16daef3a-922c-4d92-b430-bcf01edecf35.jpg" width=30% height=30%>
<img src="https://user-images.githubusercontent.com/45296858/217479515-cddb7545-be07-46a3-b200-33773f24d426.jpg" width=30% height=30%>

## Bluetooth Serial Terminal
<img src="https://user-images.githubusercontent.com/45296858/217479696-9e240e6d-fb73-463a-970b-4f19813a46bd.jpg" width=30% height=30%>
<img src="https://user-images.githubusercontent.com/45296858/217479719-5d1fb895-9280-454d-b35b-145f26c6b596.jpg" width=30% height=30%>

## How to use
To get benefits of this project:
* Connect the hardware modules like the attached help (info) and photoes to this project.
* Plugin (connect) Arduino Board to your pc / laptop.
* Download Arduino IDE (according to your system configs) from https://www.arduino.cc/en/donate/
* Copy and paste code in Controller.ino to Arduino IDE
* Verify and Upload code to the connected Arduino Board (Install "Keypad from Stan..." and "Arduino Uno" if needed).
* Open Serial Console and try using it.


## Completing Notes
* We used Fingerprint Sensor instead of mobile app.
* We wanted to use Light Sensor instead of CO Detection Sensor, but unfortunately it damaged.
* We want to use Bluetooth Sensor for additional score, to show a UI/UX for our elevator.
* We have made a Web Application for the previous task.
* We have used Arduino instead of Raspberry Pi. The reasons are:

  * Arduino gives us a better sense of working with a hardware material.
  * Raspberry Pi needs more initial configurations, and needs monitor for the first time use.
  * Compiling codes in Arduino is much more easier.

## Youtube video
Here you can see the video result of the project:
* https://www.youtube.com/watch?v=x7aLONpJMVo

[![Youtube Video](https://img.youtube.com/vi/x7aLONpJMVo/0.jpg)](https://www.youtube.com/watch?v=x7aLONpJMVo)


## TODO
 - [x] Some wires and a battery for remote controller. 
 - [x]  How to work with bluetooth or wifi module.
 - [x]  How to work with rellay and remote modules.
 - [x] Connect mobile to bluetooth module for web application. -> Web application is created by it is not connected to our modules.
 - [x] Complete code for connceting fingerprint module.
 - [x] Report -> Deadline: Bahman 18th
