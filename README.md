# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
####  DATE: 08/04/2024

####  NAME: PRASANNA R
####  ROLL NO : 212221220039
####  DEPARTMENT: IT

### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int in1=5;
int in2=6;
int en=3;
void setup()
{
  pinMode(in1,OUTPUT);
  pinMode(in2,OUTPUT);
  pinMode(en,OUTPUT);
}
void loop()
{
  analogWrite(en,50);
  
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  delay(500);
}

```
### OUTPUT
#### CIRCUIT:
<img width="474" alt="Screenshot 2024-04-05 155508" src="https://github.com/Prasanna-936/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/130341982/88887b09-283d-49ba-aeb6-70e5a31e6118">


#### SCHEMATIC DIAGRAM:
<img width="661" alt="image" src="https://github.com/Prasanna-936/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/130341982/bf9d4279-28fe-4ac0-a71e-79f6aefb856e">

### GRAPH AND TABULATION 
![WhatsApp Image 2024-04-05 at 16 12 59_a2402f21](https://github.com/Prasanna-936/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/130341982/e806c340-2776-4af8-8f69-c08f5053cbcd)

![WhatsApp Image 2024-04-05 at 16 12 57_d404d2a7](https://github.com/Prasanna-936/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/130341982/791f0138-3777-48c6-b2e9-bbc4ef700728)

### RESULTS AND DISCUSSION 
Control of the speed and the direction of a DC motor using L293D driver ic( H- bridge) is successfully executed

