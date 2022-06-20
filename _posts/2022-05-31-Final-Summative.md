---
layout: post
title: Final Summative; Mesurio | May 30 - June 17
---

### Its time to showcase everything we've learned this course!

```
#include<UltraDistSensor.h>		// include UltraDistSensor library
#include <Wire.h>				// include Wire library
#include <LiquidCrystal_I2C.h>		// include LiquidCrystal I2C library

LiquidCrystal_I2C lcd(0x27,20,4);	// Declare Pins on Arduino UNO Board

UltraDistSensor mysensor;		// Variable name is “mysensor”
float reading;				// Float allows for decimals.

const int trigPin = 12;			// Declare Pins on Arduino UNO Board
const int echoPin = 13;			// Declare Pins on Arduino UNO Board

const int LED1 = A0;			// Declare Pins on Arduino UNO Board
const int LED2 = A1;			// Declare Pins on Arduino UNO Board


int duration = 0;				// integer type, set at 0 to hold values
int distance = 0;				// integer type, set at 0 to hold values

void setup() {
    lcd.init();                     // initialize the lcd
    lcd.backlight();			// initialize/ON the light at the back
    Serial.begin(9600);			// How fast data is to be sent.
    mysensor.attach(12,13);         // Trigger pin , Echo pin

  pinMode(trigPin , OUTPUT);		// Trigger pin used as an OUTPUT device
  pinMode(echoPin , INPUT);		// Echo pin used as an INPUT device

  pinMode(LED1 , OUTPUT);		// LED1 pin used as an OUTPUT device
  pinMode(LED2 , OUTPUT);		// LED2 pin used as an OUTPUT device
}

void loop() {


    Wire.setClock(10000);		// Clock freq for I2C devices. (Hz)

     lcd.setCursor(2,0);			// Sets cursor to 2nd pixel, first row.
     lcd.print("> Distance <");	// Prints “ > Distance < “

    reading=mysensor.distanceInCm();	// Takes reading in Centimeters
     lcd.setCursor(0,1);			// First pixel, second line.
     lcd.print("In CM: ");		// Prints “In CML “”
      lcd.print(reading);		// Prints CM reading in the same line.
      lcd.print(" CM");			// prints “ CM” in the same line.

    reading=mysensor.distanceInInch();	// Takes reading in Inches
     lcd.setCursor(0,2);			// First pixel, third line.
     lcd.print("In Inches: ");		// Prints “In Inches: “
      lcd.print(reading);		// Prints IN reading in the same line.
      lcd.print(" IN");			// Prints “ IN” in the same line.

    reading=mysensor.distanceInCm();	// Takes reading in Centimeters
     lcd.setCursor(0,3);			// First pixel, fourth line
     lcd.print("In Meters: ");		// Prints “In Meters: “
      lcd.print(reading/100);		// Prints CM reading but conv. to meters.
      lcd.print(" M");			// Prints “ M” in the same line.

digitalWrite(trigPin, LOW);		// Toggles trig pin OFF
  delayMicroseconds(1000);		// Waits 1000ms
  digitalWrite(trigPin, HIGH);		// Toggles trig pin ON
  delayMicroseconds(1000);		// Waits 1000ms
  digitalWrite(trigPin, LOW);  	// Toggles trig pin OFF

  if ( mysensor.distanceInCm() <= 180 )	// if the distance is <= to 180...
  {
    digitalWrite(LED1, LOW);		// LED1 OFF
    digitalWrite(LED2, HIGH);		// LED2 ON
  }
  else						// If it’s greater than 180 CM...
  {
    digitalWrite(LED2, LOW);		// LED2 OFF
    digitalWrite(LED1, HIGH);		// LED1 ON
    lcd.clear();				// CLEARS LCD READINGS
    lcd.print("OUT OF RANGE");		// Prints “OUT OF RANGE”
  }
    delay(1500);				// Wait’s 1500ms
    lcd.init();                     // initialize the lcd
    lcd.backlight();			// turns on backlight
    Serial.begin(1000);			// sends data 1000ms
    mysensor.attach(12,13);		// sensor pins

USED THIS PART OF CODE BECAUSE OF KILLSWITCH AND US NEEDING TO TURN ON THE LCD AGAIN!

}
```
