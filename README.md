# EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor
 ###  DATE: 11.3.2024

###  NAME:DHINESH R 
###  ROLL NO :212223220019
###  DEPARTMENT:IT
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
int echopin=6;
int trigpin=7;
int red=8;
int green=9;
long duration;
float distance;
void setup()
{
pinMode(echopin,INPUT);
pinMode(trigpin,OUTPUT);
pinMode(red,OUTPUT);
pinMode(green,OUTPUT);
Serial.begin(9600);
}
void loop()
{
digitalWrite(trigpin,LOW);
delay(10);
digitalWrite(trigpin,HIGH);
delay(10);
digitalWrite(trigpin,LOW);
duration=pulseIn(echopin,HIGH);
distance=duration*0.034/2;
Serial.print("distance=");
Serial.print(distance);
Serial.println("cms");
if(distance>50)
{
  digitalWrite(green,HIGH);
  delay(500);
  digitalWrite(green,LOW);
  delay(500);
}
else
  digitalWrite(red,HIGH);
  delay(500);
  digitalWrite(red,LOW);
  delay(500);
}

```


### Distance vs measurement table 
![WhatsApp Image 2024-03-11 at 11 57 13_87be4819](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/0fc93370-8f07-46d2-ad56-9f4c8b7016f5)

   Average error = sum/ number of readings

### Graph :
![WhatsApp Image 2024-03-11 at 11 57 16_863c06b3](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/813d6cd6-e9c7-45ed-af32-2ad3d5e371ec)

### STIMULATION OUTPUT
## OFF Condition
![WhatsApp Image 2024-03-11 at 11 57 15_251f57e4](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/a30db90d-21bc-4370-a60e-a6f463b9f2b6)

## ON Condition(distance<50,green)
![WhatsApp Image 2024-03-11 at 11 57 16_6b0a46d8](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/17884837-5b64-44f6-bb0d-1b69cba48917)

## ON Condition(distance>50,red)
![WhatsApp Image 2024-03-11 at 11 57 17_facdc8ce](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/87289ec6-af8a-4190-9515-05b846f978cd)

### Schematic Representation :
![WhatsApp Image 2024-03-11 at 11 58 52_dbc60560](https://github.com/Dhinesh2301/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151379545/1991dd67-5db9-4042-b92c-a83bf9531be5)


### RESULTS
Ultrasonic Sensor is interfaced with digital output and error is identified to be 0.412 cm.




 
