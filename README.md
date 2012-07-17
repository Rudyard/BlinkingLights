BlinkingLights
==============

// Arduino programs for LED control

/*
  Blink Random
  Author Rudyard
  Randomly sswitches one red and one yellow LED on and off, with random time periods and brightnesses. It is strangely compelling.
 
  This example code is in the public domain.
 */
 
// Pin 13 has an LED connected on most Arduino boards.
// give it a name:
  int yellowLED = 13;
// Using Pin 3 for the RED LED  
  int redLED = 3;
  long randOn = 0;                  // Initialize a variable for the ON time
  long randOff = 0;                 // Initialize a variable for the OFF time
 
  int randLED;

// the setup routine runs once when you press reset:
void setup() {                
// initialize the digital pin as an output.
  randomSeed (analogRead (0));    // randomize
  pinMode(yellowLED, OUTPUT);        // sets the digital pin as output  
  pinMode(redLED, OUTPUT);        // sets the digital pin as output  

}

// the loop routine runs over and over again forever:
void loop() {
  randOn = random (10, 2400);    // generate ON time between 0.1 and 1.2 seconds
  randOff = random (200, 2400);    // generate OFF time between 0.2 and 0.9 seconds
//
/* this is the non-random blinking of the original blink
  digitalWrite(yellowLED, HIGH);   // sets the LED on
  delay(randOn);                // waits for a random time while ON
  digitalWrite(yellowLED, LOW);    // sets the LED off
  delay(randOff);               // waits for a random time while OFF
//  
  randOn = random (100, 1200);    // generate ON time between 0.1 and 1.2 seconds
  randOff = random (200, 900);    // generate OFF time between 0.2 and 0.9 seconds
//

  digitalWrite(redLED, HIGH);   // sets the LED on
  delay(randOn);                // waits for a random time while ON
  digitalWrite(redLED, LOW);    // sets the LED off
  delay(randOff);               // waits for a random time while OFF
  end */

// This is the randon stuff 
  if (random(0, 2000) > 1000)
  {
  analogWrite(yellowLED, randOn);   // sets the LED on with random intensity
  delay(randOn);                // waits for a random time while ON
  digitalWrite(yellowLED, LOW);    // sets the LED off
  delay(randOff);               // waits for a random time while OFF
  }else{
  analogWrite(redLED, randOn);   // sets the LED on with random intensity
  delay(randOn);                // waits for a random time while ON
  digitalWrite(redLED, LOW);    // sets the LED off
  delay(randOff);               // waits for a random time while OFF
  }
 
  }
//

