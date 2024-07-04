# servo-motor-control
controlling 6 servo motors using a potentiometer  


a servo motor is used to give a precise control of the angular position

I designed a circuit that consists of 6 servo motors and 6 potentiometers, each potentiometer used to control the angular position of one servo motor ranging from 0 to 180.
I used a voltage regulator to  maintain a 5 voltage since the servo motor operates between 4 and 7 V power supply.

here is the designed circuit using Tinkercad

![servoMotorControl (1)](https://github.com/FaisalBaqutyan/basic-robot-walking-algorithm/assets/174335196/7529c36f-cadc-4ef8-bfb3-d89c738a2859)


here is the Arduino code 

```
// C++ code
//
#include <Servo.h>


int potitiometer1Val = 0;

int potitiometer2Val = 0;

int potitiometer3Val = 0;

int potitiometer4Val = 0;

int potitiometer5Val = 0;

int potitiometer6Val = 0;

int servo1Val = 0;

int servo2Val = 0;

int servo3Val = 0;

int servo4Val = 0;

int servo5Val = 0;

int servo6Val = 0;

Servo servo_3;

Servo servo_5;

Servo servo_6;

Servo servo_9;

Servo servo_10;

Servo servo_11;

void setup()
{
  pinMode(A0, INPUT);
  servo_3.attach(3, 500, 2500);
  pinMode(A1, INPUT);
  servo_5.attach(5, 500, 2500);
  pinMode(A2, INPUT);
  servo_6.attach(6, 500, 2500);
  pinMode(A3, INPUT);
  servo_9.attach(9, 500, 2500);
  pinMode(A4, INPUT);
  servo_10.attach(10, 500, 2500);
  pinMode(A5, INPUT);
  servo_11.attach(11, 500, 2500);
}

void loop()
{
  potitiometer1Val = analogRead(A0);
  servo1Val = map(potitiometer1Val, 0, 1023, 0, 180);
  servo_3.write(servo1Val);
  potitiometer2Val = analogRead(A1);
  servo2Val = map(potitiometer2Val, 0, 1023, 0, 180);
  servo_5.write(servo2Val);
  potitiometer3Val = analogRead(A2);
  servo3Val = map(potitiometer3Val, 0, 1023, 0, 180);
  servo_6.write(servo3Val);
  potitiometer4Val = analogRead(A3);
  servo4Val = map(potitiometer4Val, 0, 1023, 0, 180);
  servo_9.write(servo4Val);
  potitiometer5Val = analogRead(A4);
  servo5Val = map(potitiometer5Val, 0, 1023, 0, 180);
  servo_10.write(servo5Val);
  potitiometer6Val = analogRead(A5);
  servo6Val = map(potitiometer6Val, 0, 1023, 0, 180);
  servo_11.write(servo6Val);
  delay(10); // Delay a little bit to improve simulation performance
```
