---
layout: post
title: Final Summative; Mesurio | May 30 - June 17
---

### Its time to showcase everything we've learned this course!

This class's final summative is to build something that would help someone in their day to day life. This project should actually function, in its intended role and be something that makes some task, practice, or aspect of your daily life easier, simpler, more comfortable.

**_Working with: Dev & Dhairya_**

Now this summative was very exiting from the very beginning as creating something using our knowledge thus far which can make a real world impact was amazing. With htis newfound excitement we began to brainstorming a couple of ideas that we could realistically make with our budget and time span.

**The Original Idea We Brainstormed:**

- LASER Tripwire Alarm
  - Arduino UNO
  - Seeed Studio Grove - Light Sensor
  - ky 008 Laser emitter
  - Buzzer
  - Push Button
  - 4x4 Keypad Matrix

<div style="width:100%;height:480px;background-color:white;text-align:center;">
  <a href="https://lh3.googleusercontent.com/nDBOFaoul34ORTvd4ipvzSURRAvf9upkcDeBIRT7kDFFRNBUh6z3oGCwhApLBq7XYqfsPyWR2AnSBC0UJk4aBpEFi-R9hdYOM_j162hyN7XKW9gfJiNHe6QNv8djHfYgqvXpA__gGQ=w1920-h1080" target="_blank">
    <img style="height:100%;border:0;" src="https://lh3.googleusercontent.com/nDBOFaoul34ORTvd4ipvzSURRAvf9upkcDeBIRT7kDFFRNBUh6z3oGCwhApLBq7XYqfsPyWR2AnSBC0UJk4aBpEFi-R9hdYOM_j162hyN7XKW9gfJiNHe6QNv8djHfYgqvXpA__gGQ=h480" />
  </a>
</div>

### However this idea couldn't come to fruition!

We didn't let this set us back, rather we worked hard and came up with another idea inspired by Mr. Chauhans suggestion: **Mesurio!**

Ever want to measure the distance between you and an object? Measuring tapes too hard to use? Too flimsy, hard to latch on surfaces? Well **Mesurio** is the perfect solution! Introducing an electronic distance measurement device that provides fast, on screen displays in 3 units of measurement (centimeters, inches & meters) supporting all measurement systems! Mesurio holds the capability to accurately measure up to 1.9 meters. All this is done with a compact device you can comfortable hold in you hands, and when you're not hold it you can place it onto its docking station and continue about your day! **_Our solution helps makes day to day tasks for many professionals easier, is very polished and aestheticlly pleasing!_**

**We started by gathering the needed materials:**

- Arduino UNO
- 2 LED’s (Green & Red)
- Kill Switch
- Ultrasonic Distance Sensor
- LCD I2C Display
- 9V Battery
- Jumper Wires
- Arduino IDE

**Next we make the TinkerCAD schematic:**

<div style="width:100%;height:480px;background-color:white;text-align:center;">
  <a href="https://lh3.googleusercontent.com/IRZAl5-bP7jSaTQPB3AeUV9D--ksln5rSBulMp7rh54m0dAXdW2JvD0mEN3RzhC0SUZQZFGZU7mWFJewDCbagSbU7atghFH6hZFmBao91B4ethp4NVQcMDuSh4bXZnvMV-mwT-Fl7g=w1920-h1080" target="_blank">
    <img style="height:100%;border:0;" src="https://lh3.googleusercontent.com/IRZAl5-bP7jSaTQPB3AeUV9D--ksln5rSBulMp7rh54m0dAXdW2JvD0mEN3RzhC0SUZQZFGZU7mWFJewDCbagSbU7atghFH6hZFmBao91B4ethp4NVQcMDuSh4bXZnvMV-mwT-Fl7g=h480" />
  </a>
</div>

**Create the Code to ensure our TinkerCAD circuit is functional:**

```
#include<UltraDistSensor.h>		// include UltraDistSensor library
#include <Wire.h>				// include Wire library
#include <LiquidCrystal_I2C.h>  // include LiquidCrystal I2C library

LiquidCrystal_I2C lcd(0x27,20,4);	// Declare Pins on Arduino UNO Board

UltraDistSensor mysensor;		// Variable name is “mysensor”
float reading;				    // Float allows for decimals.

const int trigPin = 12;			// Declare Pins on Arduino UNO Board
const int echoPin = 13;			// Declare Pins on Arduino UNO Board

const int LED1 = A0;			// Declare Pins on Arduino UNO Board
const int LED2 = A1;			// Declare Pins on Arduino UNO Board


int duration = 0;				// integer type, set at 0 to hold values
int distance = 0;				// integer type, set at 0 to hold values

void setup() {
    lcd.init();                 // initialize the lcd
    lcd.backlight();			// initialize/ON the light at the back
    Serial.begin(9600);			// How fast data is to be sent.
    mysensor.attach(12,13);     // Trigger pin , Echo pin

  pinMode(trigPin , OUTPUT);    // Trigger pin used as an OUTPUT device
  pinMode(echoPin , INPUT);		// Echo pin used as an INPUT device

  pinMode(LED1 , OUTPUT);		// LED1 pin used as an OUTPUT device
  pinMode(LED2 , OUTPUT);		// LED2 pin used as an OUTPUT device
}

void loop() {


    Wire.setClock(10000);		// Clock freq for I2C devices. (Hz)

     lcd.setCursor(2,0);		// Sets cursor to 2nd pixel, first row.
     lcd.print("> Distance <");	// Prints “ > Distance < “

    reading=mysensor.distanceInCm();	// Takes reading in Centimeters
     lcd.setCursor(0,1);		// First pixel, second line.
     lcd.print("In CM: ");		// Prints “In CML “”
      lcd.print(reading);		// Prints CM reading in the same line.
      lcd.print(" CM");			// prints “ CM” in the same line.

    reading=mysensor.distanceInInch();	// Takes reading in Inches
     lcd.setCursor(0,2);		// First pixel, third line.
     lcd.print("In Inches: ");	// Prints “In Inches: “
      lcd.print(reading);		// Prints IN reading in the same line.
      lcd.print(" IN");			// Prints “ IN” in the same line.

    reading=mysensor.distanceInCm();	// Takes reading in Centimeters
     lcd.setCursor(0,3);		// First pixel, fourth line
     lcd.print("In Meters: ");	// Prints “In Meters: “
      lcd.print(reading/100);	// Prints CM reading but conv. to meters.
      lcd.print(" M");			// Prints “ M” in the same line.

digitalWrite(trigPin, LOW);		// Toggles trig pin OFF
  delayMicroseconds(1000);		// Waits 1000ms
  digitalWrite(trigPin, HIGH);	// Toggles trig pin ON
  delayMicroseconds(1000);		// Waits 1000ms
  digitalWrite(trigPin, LOW);  	// Toggles trig pin OFF

  if ( mysensor.distanceInCm() <= 180 )	// if the distance is <= to 180...
  {
    digitalWrite(LED1, LOW);	// LED1 OFF
    digitalWrite(LED2, HIGH);	// LED2 ON
  }
  else						// If it’s greater than 180 CM...
  {
    digitalWrite(LED2, LOW);	// LED2 OFF
    digitalWrite(LED1, HIGH);	// LED1 ON
    lcd.clear();				// CLEARS LCD READINGS
    lcd.print("OUT OF RANGE");	// Prints “OUT OF RANGE”
  }
    delay(1500);				// Wait’s 1500ms
    lcd.init();                 // initialize the lcd
    lcd.backlight();			// turns on backlight
    Serial.begin(1000);			// sends data 1000ms
    mysensor.attach(12,13);		// sensor pins

USED THIS PART OF CODE BECAUSE OF KILLSWITCH AND US NEEDING TO TURN ON THE LCD AGAIN!

}
```

**Start creating summative physically:**

<script src="https://cdn.jsdelivr.net/npm/publicalbum@latest/embed-ui.min.js" async></script>
<div class="pa-gallery-player-widget" style="width:100%; height:480px; display:none;"
  data-link="https://photos.app.goo.gl/txwtByyXg9vZmrWPA"
  data-title="Progress Photos - Mesurio"
  data-description="3 new items added to shared album">
  <object data="https://lh3.googleusercontent.com/PVyeqlTNCnxlGGs_wqG9yKaPPuXB9g_QqC4YKKtOBff1RtnPdIYkuGWTGpgv_Q6rIushx9BnHcL5pBFiRK4TGD7sX5zm2rUepsKzuKzgG4ZrvcE2AOSyswHznkN9-M7Ju0OfJc8sxw=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/dpesL-jz4X6xCgGGou60KfqJwkcgd7_NB6G_3XplEsIrQzAjhbi8vqwn3KoLSlAejGeKGjelripP2DvwHxeKiqpZhtVjn6Gki5ofXRbal7mavi08uBGNVCySKAHL8jtiWrjrjXwqgQ=w1920-h1080"></object>
  <object data="https://lh3.googleusercontent.com/QHcMaogX5KNDvSIMRprB6S4mIhlbO9yvRPI3YxsdHfKBtpqG_NQAEOVqHgyvmMFgXTgk1tNftN0BYbuIcJUl_r8-D9Ol86ztdeiOE6yo-bUbOVfn1xsNW60L6BYkBbfvZ_BPwNhR7g=w1920-h1080"></object>
</div>

### We're Done!

The joy of creating such a device which I once would've thought is impossible for me to even imagine was soon diminised at the realization that this course has come to an end along with this assignment. However this assignment was amazing, despite the adversity we faced we were able to overcome it all and be victorious at the end of it all! I gained a deeper appreciation for computer engineers and learned more then I could've ever thought was possible. I thank you Mr. Chauhan for this oppourtunity 🙏🏽
