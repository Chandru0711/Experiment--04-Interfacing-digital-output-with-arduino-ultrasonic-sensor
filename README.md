# EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor

## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)

![Screenshot 2024-03-07 062304](https://github.com/Chandru0711/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/144979368/95185d79-43e2-4f3d-b1ae-dae2dcf824ac)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM
```
const int trigpin=10;
const int echopin=9;
int red=7;
int green=6;
long duration;
int distance;

void setup()
{
  pinMode(trigpin, OUTPUT);
    pinMode(echopin, INPUT);
    pinMode(red, OUTPUT);
    pinMode(green, OUTPUT);
  Serial.begin(9600);
  




}

void loop()
{
  digitalWrite(trigpin, LOW);
  delay(20); 
  digitalWrite(trigpin, HIGH);
  delay(20);
    digitalWrite(trigpin, LOW);
duration=pulseIn(echopin,HIGH);
  distance=duration*0.034/2;
  Serial.print(distance);
  Serial.println("cms");
  if(distance>5)
  {
     digitalWrite(red, HIGH);
  delay(200); 
   digitalWrite(red, LOW);
  delay(200);
  }
  else
  {
     digitalWrite(green, HIGH);
  delay(200); 
   digitalWrite(green, LOW);
  delay(200); 
  }
}
```




### Distance vs measurement table 

![tab](https://github.com/Chandru0711/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/144979368/66e907a6-77fb-4e2e-82e4-efa4b3260acc)
			
 
			
			
			
![grap](https://github.com/Chandru0711/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/144979368/88310b05-7d3a-4d86-9665-54cac1d37d4b)
			
			
			
			
			
			Average error = sum/ number of readings 
 








### RESULTS
Thus the program for the distance measurement using Ultrasonic sensor is been implemented successfully.


 
