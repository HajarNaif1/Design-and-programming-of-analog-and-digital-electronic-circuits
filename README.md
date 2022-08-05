# Design and programming of analog and digital electronic circuits:

#### :one: Distance measurement of the type of analog :bulb: :
##### - *Explanation of the circuit* :mag_right: :
###### The function of the circuit is to measure the distance between the sensor and an obstacle, and print the result on the serial monitor screen
##### - *used gear* :
###### :small_orange_diamond: Arduino UNO board, or any board compatible with it.
###### :small_orange_diamond: Electronic workout board.
###### :small_orange_diamond: Jumper-Wire connection wires.
###### :small_orange_diamond: Ultrasonic distance sensor.

##### - *gear connection* :
###### :small_orange_diamond: Connect 5V, GND to the distance sensor.
###### :small_orange_diamond: Connect the trig insert to a digital insert that works in the output mode, let it be the number 8 insert.
###### :small_orange_diamond: Connect the echo pin to a digital pin that works in the input mode, let it be the pin number 9.

##### - *The shape of the general circuit diagram is* :
![image](https://user-images.githubusercontent.com/107880209/182977989-2574d8e5-8673-4572-b036-fe47a1240853.png)
##### - *The circuit form is practically as follows* :
![nalog-type distance measurement circuit design](https://user-images.githubusercontent.com/107880209/182978114-fc4a0c52-e1c4-4b0e-a9b6-ccb5b5ee4afe.png)

##### - *code* :
```
// Ultrasonic Sensor HC-SR04 and Arduino
// defines pins numbers
int Trig = 8;
int Echo = 9;
// defines variables
long Time;
int Distance;
void setup() {
pinMode(Trig, OUTPUT); // Sets the trig Pin as an Output
pinMode(Echo, INPUT); // Sets the echo Pin as an Input
Serial.begin(9600); // Starts the serial communication
}
void loop() {
  
// Clears the trig Pin
digitalWrite(Trig, LOW);
delayMicroseconds(2);
// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(Trig, HIGH);
delayMicroseconds(10);
digitalWrite(Trig, LOW);
// Reads the echo Pin, returns the sound wave travel time in microseconds
Time = pulseIn(Echo, HIGH);
Time = Time /2;
// Calculating the distance
Distance= Time*0.034;
// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(Distance);
}
```
##### - *Summary* :
###### :small_orange_diamond: We were able to measure the distance using an ultrasonic sensor, a method widely used in embedded systems, especially in modern cars and robotics.
###### :small_orange_diamond: The measurement results are affected if the sensor is tilted at a large angle from the obstacle, and therefore the entire wave does not return to the receiving unit.
###### :small_orange_diamond: There is also a type of ultrasonic sensor called PING, which is the same principle as the sensor mentioned in the article, but by connecting the Trig and Echo implants together, and thus a piece of software is added that works to transfer the state of the digital implant between two input or output states constantly so that the implant works sometimes as Trig and sometimes Others such as Echo.

##### - *To see the result, click on the link* :
###### https://www.tinkercad.com/things/gCpxC20Axve



#### :two: Digital temperature sensor :bulb: :
