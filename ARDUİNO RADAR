
#include <LiquidCrystal.h>         // the LCD Library
#include <NewPing.h>               // the Ultrasonic Library

#define TRIG  3                    // Pin-3 of Arduino Connected to Trig Pin of Ultrasonic
#define ECHO  2                    // Pin-4 of Arduino Connected to Echo Pin of Ultrasonic
#define MAX_DISTANCE 100           // Max. Distance the Sensor Can Measure, Required for the Library


NewPing sonar(TRIG, ECHO, MAX_DISTANCE); // Ultrasonic Variable
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);  // LCD Variable


unsigned int duration;             // Variable Used To Store The Measured Distance

void setup()
{
 pinMode(TRIG,OUTPUT);             // Set Trig Pin of Arduino As Output
 pinMode(ECHO, INPUT);             // Set Echo Pin of Arduino As Input
 lcd.begin(16,2);                  // To Setup and Start the LCD
 lcd.clear();                      // To Clear the LCD
}

void loop()
{
 duration = sonar.ping();          // Send ping, get ping time in microseconds (uS).
 duration = duration / 2 / 29.4;   // Explained Below
 lcd.print("Ping: ");              // to Print " Ping:  " on the LCD
 lcd.print(duration);              // next to it print the Calculated Value
 lcd.print(" cm");

 // on lcd we will see "  Ping: 30 cm  "

 delay(1000);                      // min. delay between pings is 29 msec
 lcd.clear();                      // to clear the LCD for the Next Round
}
